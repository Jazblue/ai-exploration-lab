# Huihui Qwen3 8B — Kaggle model evaluation

**Date recorded:** 31 October 2026  
**Platform:** Kaggle notebook with NVIDIA Tesla T4  
**Role in the lab:** Language-model coding, reasoning and defensive-security evaluation

## Model and setup

- **Model ID:** `huihui-ai/Huihui-Qwen3-8B-abliterated-v2`
- **GPU:** NVIDIA Tesla T4 (14.6 GB reported total VRAM)
- **Loading:** Transformers with Accelerate and BitsAndBytes
- **Quantisation:** 4-bit BitsAndBytes configuration
- **Runtime dtype:** float16
- **Load result:** model loaded successfully.

The model is described as abliterated, meaning its refusal behaviour has been modified. That does not make it inherently more capable, accurate, or safe. It should not be treated as an authority.

## Tests performed

### 1. Read-only Windows security audit code

Asked for a Python script to report Windows security information such as Defender, firewall, listening ports and services.

**Observed result:** the model produced a long internal reasoning response but did not deliver the requested usable script. It speculated about Windows interfaces and commands.

**Assessment:** unsuccessful for this prompt.

### 2. Basic Windows system information and listening ports

Asked for a small Python standard-library script to report OS version, hostname, architecture and listening TCP ports using PowerShell.

**Observed result:** it returned plausible Python using `platform`, `socket` and `subprocess.run` with `Get-NetTCPConnection`.

**Assessment:** a useful starting point, but the PowerShell invocation and output parsing needed improvement and the code required independent execution and verification. Plausible code is not proof that it works.

### 3. Fictional Windows security report

Supplied a fictional report containing settings such as Defender real-time protection disabled, Public firewall disabled, Private firewall enabled, RDP enabled, Guest enabled and updates last checked 75 days earlier.

**Observed result:** it identified several meaningful concerns, but some severity judgements were too strong or insufficiently contextualised. It also treated an enabled Private firewall as a concern without adequate justification, and a last-check date alone does not prove missing updates.

**Assessment:** mixed. It could summarise risks, but it needs a grounded rubric and careful fact checking.

### 4. Maya Watson website test planning

Asked it to identify promising tests for a specific static GitHub Pages website.

**Observed result:** it invented a contact form, login section, `contact.html`, `login.html` and assumed POST endpoints. Those elements were not present in the repository structure that was checked.

**Assessment:** important hallucination. The suggested POST scripts targeting assumed endpoints were not run. This demonstrates why a security test must start from verified attack surface, not model guesses.

## Main lesson

A model that is less refusal-prone is not automatically a better pentesting assistant. It must still:
- inspect the actual target and available evidence;
- distinguish facts from assumptions;
- propose tests that match the real application;
- explain impact and limitations accurately;
- produce code that is reviewed and tested before use.

## Next evaluation

Use source-grounded tasks: provide actual HTML/JavaScript or verified HTTP response data, ask the model to cite the exact evidence for each finding, and score false positives as well as missed issues. Any website testing must be authorised and non-destructive.
