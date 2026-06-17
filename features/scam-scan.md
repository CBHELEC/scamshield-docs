---
title: "Manual Scan"
description: "Use the /check command to manually analyze messages and images for scams."
icon: "barcode-scan"
---

# Manual Scan

The ScamScan cog provides a `/check` command for on-demand analysis of suspicious messages. This is useful for verifying messages that might have been missed by the automated engines.

## Usage

```text
/check text: <message> image: <attachment>
```

Both `text` and `image` parameters are optional, but at least one must be provided.

### Text Analysis

Analyzes the provided text against all 15\+ scam pattern groups and returns:

- **Risk Level** — Very High, High, Medium, Low, or Very Low
- **Probability** — Scam probability percentage (0–100%)
- **Matched Patterns** — List of detected pattern groups with individual scores

### Image Analysis

If an image is attached, the bot attempts OCR (Optical Character Recognition via Tesseract) to extract text from the image, then analyzes that text against the same patterns.

## Response

The command returns an ephemeral embed (only visible to the user who ran the command) with:

- Risk level indicator with color coding
- Scam probability bar
- List of matched patterns with emoji and description
- Source label (text, image, or image \+ OCR)

## Use Cases

- Verify suspicious messages that seem borderline
- Check if an image-based ad contains scam text
- Investigate user reports of potential scams
- Test detection patterns with custom messages