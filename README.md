# UFC-AI-ML-Predictor
Looking to predict the outcome of UFC fights using machine learning. This project uses a neural network trained on historical UFC fight data to estimate the probability that Fighter A will win a given matchup.

## UFC-AI-ML-Predictor
1. Matchup Detection

    Input: Fighter names or stats

    System infers:

        Style (from cluster or override)

        Age, WinStreak, TDPct, SigStr, etc.

2. Feature Extraction

For both fighters:

    Style: Grappler, Striker, Balanced

    Age, Reach, TDPct, SubAtt, SigStr

    Recent record (last 3 fights)

    Layoff (days since last fight)

    MismatchScore (calculated)

3. Maximized Model for GvS

    Train model only on GvS matchups

    Include only:

        Elite grappler flags

        MismatchScore

        TDD, SigStrDiff, and recent record

    Output: probability of Red winning

4. Explanation Module

    Return:

        Predicted win chance (e.g. 74% Red)

        Why: “Red fighter is an elite grappler facing a low-TDD striker”

        Show similar historical matchups (from your dataset)

5. Possible Enhancements

    Risk/confidence score

    Betting value signal (if Red has 74% win chance but Vegas line says 55%), maybe even build api

## Implementation Plan
Phase	Description
Phase 1	Build data pipeline to detect matchup and extract features
Phase 2	Build GvS-only model using clean features
Phase 3	Train explanation module to surface similar fights
Phase 4	Wrap in a UI (CLI/Streamlit) for input → % prediction → rationale
