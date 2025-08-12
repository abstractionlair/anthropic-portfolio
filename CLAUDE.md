# Claude Code Context

## Project Overview

You are helping build an AI-powered portfolio curation system for an Anthropic job application. This isn't just selecting best conversations—it's demonstrating systematic thinking and technical capability through the curation process itself.

## Current Project State

### Repository Structure
```
anthropic-portfolio/
├── src/                          # Scoring system implementation
│   ├── score_conversations.py   # Main scoring pipeline
│   └── requirements.txt         # Python dependencies
├── gold_standards/              # Manually selected excellent conversations
├── portfolio/                   # Final curated conversations (to be populated)
├── README.md                    # Project narrative and overview
├── PLAN.md                      # Detailed project plan
├── THE_CHALLENGE.md            # Methodology documentation
├── FUTURE_WORK.md              # Internal states proposal
└── CLAUDE.md                   # This file - your context
```

## Your Role

You're the technical implementation partner. The human will:
1. Provide gold standard conversations
2. Point to their corpus location
3. Request specific features or fixes

You should:
1. Implement robust, production-quality code
2. Handle edge cases (rate limits, errors, resumability)
3. Create clear visualizations and reports
4. Ensure the code demonstrates technical excellence

## Key Technical Requirements

### Scoring System
- **Input**: Directory of conversation files (txt, md, json)
- **Process**: Score via Anthropic API using multi-dimensional rubric
- **Output**: JSON with scores + human-readable reports

### Scoring Dimensions
1. **Intellectual Depth** (30%): Evolution of ideas
2. **Originality** (30%): Novel frameworks
3. **Technical Precision** (20%): Rigor and accuracy
4. **Relevance to Anthropic** (20%): Alignment with company mission

### Categories (Taxonomy)
- `foundation`: Learning established concepts
- `deep_understanding`: Probing why things work
- `speculative_innovation`: Novel proposals
- `philosophy_safety`: Hard questions
- `innovative_usage`: Pioneering workflows
- `convergent_discovery`: Reinventing known concepts
- `meta_cognition`: AI studying AI

## Implementation Priorities

1. **Robustness**: This needs to work on 2000+ files without failing
2. **Resumability**: Can restart from interruption
3. **Transparency**: Clear logging and progress indication
4. **Analysis**: Rich statistics and visualizations
5. **Reproducibility**: Others can run this on their own corpus

## Current Implementation Status

- ✅ Basic scoring pipeline structure
- ⚠️ Needs: Error handling improvements
- ⚠️ Needs: Resume capability
- ⚠️ Needs: Visualization generation
- ⚠️ Needs: HTML report output

## API and Environment

- Uses Anthropic API (claude-3-5-sonnet-20241022)
- Expects `ANTHROPIC_API_KEY` environment variable
- Rate limiting: ~1 second between calls
- Budget: ~$20-30 for full corpus

## Next Steps

When the human returns with gold standards:
1. Create a calibration module that validates scoring consistency
2. Add resume capability (save progress to checkpoint file)
3. Generate visualization of score distributions
4. Create HTML portfolio browser
5. Add category-based selection logic

## Quality Bar

This code is part of a job application to Anthropic. It should demonstrate:
- Clean, well-documented Python
- Thoughtful error handling
- Efficient API usage
- Clear separation of concerns
- Useful comments explaining "why" not just "what"

## Remember

The meta-goal is showing how to identify and evaluate intellectual quality in AI conversations at scale. The code itself is a demonstration of technical capability.

## File Formats

### Expected Conversation Format
Flexible - the system should handle:
- Plain text files
- Markdown with conversation structure
- JSON with message arrays
- Various naming conventions

### Output Format
```json
{
  "analysis": {
    "total_conversations": 2000,
    "portfolio_worthy_count": 25,
    "score_statistics": {...},
    "category_distribution": {...}
  },
  "scores": [
    {
      "file_path": "path/to/conversation.md",
      "intellectual_depth": 8.5,
      "originality": 7.0,
      "technical_precision": 9.0,
      "relevance_to_anthropic": 8.0,
      "overall_score": 8.1,
      "primary_category": "deep_understanding",
      "key_quote": "...",
      "portfolio_worthy": true
    }
  ]
}
```

## Testing Strategy

Before running on full corpus:
1. Test on 5-10 files first
2. Verify scoring consistency
3. Check resume capability
4. Validate output format
5. Then run on full corpus

---

*This context file helps Claude Code understand the project instantly when opened in a new session.*