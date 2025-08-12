# Data Structure Guide

## Directory Layout

This project expects conversations to be organized as follows:

### Within Repository
```
anthropic-portfolio/
├── gold_standards/          # Your manually selected best conversations
│   ├── 01_transformers_why.md
│   ├── 02_vectors_proto_words.md
│   ├── 03_constitutional_ai_discovery.md
│   └── ...                 # 10-15 total files
└── portfolio/              # Final selections (populated by system)
    ├── 01_foundation/
    ├── 02_deep_understanding/
    └── ...                 # Organized by category
```

### Outside Repository (Local Only)
```
~/conversations_corpus/      # Or your preferred location
├── 2024/
│   ├── january/
│   ├── february/
│   └── ...
├── 2025/
│   ├── january/
│   └── ...
└── unsorted/
    └── ...                 # Any structure works
```

## File Formats Supported

### Text Files (.txt)
```
Human: [Question about transformers]

Assistant: [Response explaining transformers]

Human: [Follow-up question]

Assistant: [Deeper explanation]
```

### Markdown Files (.md)
```markdown
# Conversation Title

## Human
[Question or prompt]

## Assistant
[Response]

## Human
[Follow-up]
```

### JSON Files (.json)
```json
{
  "messages": [
    {"role": "human", "content": "..."},
    {"role": "assistant", "content": "..."},
    {"role": "human", "content": "..."}
  ],
  "metadata": {
    "date": "2024-01-15",
    "model": "claude-3"
  }
}
```

## Naming Conventions

No strict requirements, but helpful patterns:
- Include date: `2024-01-15_transformers.md`
- Include topic: `decision_theory_evolution.txt`
- Include model: `claude3_consciousness_discussion.json`

## Gold Standards Selection

When selecting your 10-15 gold standard conversations:

1. **Rename them descriptively**:
   - `01_transformers_why_not_how.md`
   - `02_constitutional_ai_convergent.md`
   - `03_meta_curation_project.md`

2. **Cover diverse categories**:
   - 2-3 deep_understanding
   - 2-3 innovation
   - 1-2 philosophy_safety
   - 1-2 convergent_discovery
   - 1-2 meta_cognition
   - 1-2 foundation

3. **Include variety**:
   - Different lengths (short insights and long explorations)
   - Different models if available
   - Different time periods

## Privacy Considerations

### Before Adding to Repository

1. **Remove personal information**:
   - Names (except public figures)
   - Email addresses
   - Phone numbers
   - Addresses
   - Company confidential information

2. **Sanitize if needed**:
   ```python
   text = text.replace("actual_email@domain.com", "[email]")
   text = text.replace("ClientCompanyName", "[Client]")
   ```

3. **Keep valuable content**:
   - Technical discussions are fine
   - Philosophical explorations are fine
   - Even controversial topics if thoughtfully engaged

## Corpus Preparation Checklist

- [ ] Conversations gathered in single directory tree
- [ ] Verified file formats (.txt, .md, or .json)
- [ ] No corrupted or empty files
- [ ] Personal information removed/sanitized
- [ ] Gold standards selected and copied to `/gold_standards/`
- [ ] Path to corpus noted for scoring script

## Running the Scorer

Once organized:
```bash
cd src/
python score_conversations.py \
    --input_dir ~/conversations_corpus \
    --gold_standards ../gold_standards \
    --output results.json
```

## Expected File Sizes

- Individual conversations: 1KB - 50KB typically
- Gold standards folder: ~200KB (10-15 files)
- Full corpus: Variable (2000 files ≈ 20-100MB)
- Results JSON: ~2-5MB for 2000 conversations

---

*This guide ensures consistent data handling across the project.*