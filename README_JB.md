# JJ Bumrah Bowling Analysis

## 📊 Comprehensive IPL Performance Analysis (2013-2025)

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![ML](https://img.shields.io/badge/Machine%20Learning-K--Means-green.svg)](https://scikit-learn.org/)
[![Status](https://img.shields.io/badge/Status-Complete-success.svg)]()

> A data-driven analysis of JJ Bumrah's bowling performance across 145 Mumbai Indians matches, combining statistical analysis with machine learning to uncover what makes him one of the most effective T20 bowlers.

---

## 🎯 Project Overview

This project analyzes **12+ years** of JJ Bumrah's IPL career using **3,474 deliveries** across **145 matches** to answer:

- ✅ What makes JJ Bumrah effective as a T20 bowler?
- ✅ Where does he struggle?
- ✅ How has his performance evolved over time?
- ✅ What patterns exist in his dominant vs struggling performances?

### Key Finding: **"The All-Phase Specialist"**

Unlike typical T20 bowlers, Bumrah maintains **elite performance across ALL phases**:
- **Powerplay**: 6.64 economy, 49% dot balls
- **Middle Overs**: 6.59 economy (best phase)
- **Death Overs**: 8.22 economy, 98 wickets (most lethal)

---

## 📁 Project Structure

```
MI_json/
│
├── JB.ipynb                    # Main analysis notebook
├── README_JB.md               # This file
├── *.json                     # 277 match data files (Cricsheet format)
└── README.txt                 # Data source documentation
```

---

## 📈 Analysis Components

### 1. **Data Extraction & Preparation**
- **Source**: 277 Mumbai Indians IPL matches (2008-2025) in JSON format
- **Coverage**: 145 matches where JJ Bumrah bowled
- **Deliveries**: 3,474 balls analyzed
- **Wickets**: 203 dismissals tracked

### 2. **Statistical Analysis**

#### Phase-wise Performance
| Phase | Overs | Economy | Dot % | Wickets | Strike Rate |
|-------|-------|---------|-------|---------|-------------|
| Powerplay (0-5) | 197.83 | 6.64 | 49.37% | 43 | 27.60 |
| Middle (6-15) | 174.00 | 6.59 | 38.31% | 62 | 16.84 |
| Death (16-19) | 207.17 | 8.22 | 29.53% | 98 | 12.68 |

#### Dismissal Type Distribution
- **Caught**: 57.6% (117 wickets) - Pace & bounce threat
- **Bowled**: 23.2% (47 wickets) - Yorker mastery
- **LBW**: 8.9% (18 wickets) - Stump-to-stump accuracy
- **Others**: 10.3% (21 wickets)

#### Career Trends
- **Economy Rate**: -1.62% average yearly improvement
- **Wickets per Match**: +9.07% average yearly improvement
- **Best Year**: 2024 (6.24 economy)
- **Peak Wickets**: 2020 (2.00 per match)

### 3. **Matchup Analysis**

#### Batsmen Who Handle Bumrah Well
- **Virat Kohli**: 9.17 economy (104 balls, 5 wickets)
- **AB de Villiers**: 9.00 economy (90 balls, 3 wickets)

#### Bumrah's Dominance
- **Rishabh Pant**: 7.25 economy (48 balls, **7 wickets**)
- **MS Dhoni**: 5.91 economy (68 balls, 5 wickets)

#### Critical Weakness: Left-Handed Power Hitters
- **Chris Gayle**: 5.21 economy, **0 wickets in 53 balls**
- **David Warner**: 7.15 economy, **0 wickets in 47 balls**
- **Shikhar Dhawan**: 7.55 economy, only 1 wicket in 89 balls

### 4. **Machine Learning Analysis**

#### K-Means Clustering (Match Performance Segmentation)
- **Algorithm**: K-Means with k=3
- **Features**: 14 performance metrics per match
- **Silhouette Score**: High cluster quality
- **Clusters Identified**:
  - 🟢 **Dominant**: Economy < 6.5, 2+ wickets, 50%+ dots
  - 🟠 **Average**: Economy 7.0-7.5, 1-1.5 wickets
  - 🔴 **Struggling**: Economy 9.0+, <1 wicket

#### Cluster Insights
- **Recent years** show increasing proportion of dominant performances
- **Venue patterns** emerge: certain grounds consistently produce dominant/struggling performances
- **Opposition trends**: Specific teams trigger different performance modes

---

## 🔬 Technical Implementation

### Technologies Used
```python
# Data Processing
- pandas         # Data manipulation
- numpy          # Numerical operations
- json           # JSON parsing

# Visualization
- matplotlib     # Plotting
- seaborn        # Statistical visualization

# Machine Learning
- scikit-learn   # K-Means clustering, PCA, StandardScaler
```

### Key Methodologies

1. **Data Extraction**
   - Parsed 277 JSON files using glob
   - Extracted delivery-level data with match context
   - Identified batting positions from team lineups

2. **Feature Engineering**
   - Aggregated delivery-level to match-level features
   - Created phase classifications (Powerplay/Middle/Death)
   - Calculated 14 performance metrics per match

3. **Statistical Analysis**
   - Descriptive statistics by phase, opponent, batsman
   - Temporal trend analysis (2013-2025)
   - Head-to-head matchup calculations

4. **Machine Learning**
   - StandardScaler normalization
   - K-Means clustering with optimal k selection
   - PCA for 2D visualization
   - Silhouette score for cluster validation

---

## 📊 Visualizations

The notebook includes 9 comprehensive visualizations:

1. **Phase-wise Performance Chart** - Economy vs Dot% by phase
2. **Career Trend Line** - Economy rate evolution over 12 years
3. **Wickets by Phase** - Distribution and wickets per match
4. **Strike Rate vs Average** - Phase-wise scatter plot
5. **Elbow Curve** - Optimal cluster selection
6. **Silhouette Scores** - Cluster quality validation
7. **PCA Scatter Plot** - 2D match clustering visualization
8. **Radar Chart** - Multi-metric performance comparison
9. **Summary Infographic** - 7-panel comprehensive dashboard

---

## 🎯 Key Findings

### Strengths ✅
1. **All-Phase Consistency**: Elite performance in powerplay, middle, AND death overs
2. **Death Overs Mastery**: 98 wickets at 8.22 economy (excellent for death)
3. **Continuous Improvement**: Career trajectory shows upward trend
4. **Yorker Execution**: 23% bowled wickets (vs 15% T20 average)
5. **Pressure Building**: 39.7% overall dot ball percentage
6. **Dual Threat**: Pace/bounce (caught) + yorkers (bowled)

### Weaknesses ❌
1. **Left-Handed Power Hitters**: Never dismissed Gayle or Warner
2. **Flat Pitches**: Struggles on batting-friendly surfaces
3. **2015 Season**: Learning phase with 11.27 economy

### The One Key Tactical Insight 🎯

**"The Reverse Specialist"**

Traditional T20 bowlers are economical in one phase and expensive in others. Bumrah maintains **near-identical economy in powerplay (6.64) and middle overs (6.59)** while being the **most lethal wicket-taker in death overs** (0.68 wickets/match).

**Strategic Implication**: Batsmen cannot plan "when to attack" because he's effective everywhere, forcing high-risk shots that lead to wickets.

---

## 🚀 How to Use This Analysis

### Prerequisites
```bash
# Python 3.11+
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Running the Notebook

1. **Clone/Download the repository**
   ```bash
   cd MI_json
   ```

2. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook JB.ipynb
   ```

3. **Run All Cells**
   - Kernel → Restart & Run All
   - Wait for data extraction (processes 277 JSON files)
   - View visualizations and analysis

### Expected Runtime
- Data Extraction: ~30 seconds
- Statistical Analysis: ~10 seconds
- ML Clustering: ~5 seconds
- Visualizations: ~15 seconds
- **Total**: ~1 minute

---

## 📊 Data Source

**Cricsheet** - https://cricsheet.org/

- **Format**: JSON v1.0.0 and v1.1.0
- **Coverage**: 277 Mumbai Indians IPL matches (2008-2025)
- **License**: Open data for cricket analytics

### Data Structure
```json
{
  "meta": { "data_version": "1.0.0" },
  "info": {
    "teams": ["Mumbai Indians", "Opponent"],
    "dates": ["YYYY-MM-DD"],
    "venue": "Stadium Name",
    "players": { "Team": ["Player1", "Player2", ...] }
  },
  "innings": [
    {
      "team": "Team Name",
      "overs": [
        {
          "over": 0,
          "deliveries": [
            {
              "batter": "Batsman",
              "bowler": "JJ Bumrah",
              "runs": { "batter": 0, "extras": 0, "total": 0 },
              "wickets": [...]
            }
          ]
        }
      ]
    }
  ]
}
```

---

## 🔍 Analysis Highlights

### Career Statistics
- **Matches**: 145
- **Deliveries**: 3,474
- **Wickets**: 203
- **Economy**: 7.19
- **Strike Rate**: 17.11 balls/wicket
- **Average**: 20.5 runs/wicket
- **Dot Ball %**: 39.7%

### Comparison to T20 Standards

| Metric | Bumrah | T20 Average | Status |
|--------|--------|-------------|--------|
| Economy | 7.19 | 8.0-8.5 | ✅ Elite |
| Strike Rate | 17.11 | 20-22 | ✅ Elite |
| Dot % | 39.7% | 30-35% | ✅ Elite |
| Death Economy | 8.22 | 9.5-11 | ✅ Elite |

### Performance by Opponent (Top 5)

| Team | Matches | Economy | Wickets | Wickets/Match |
|------|---------|---------|---------|---------------|
| Kolkata Knight Riders | 18 | 7.82 | 27 | 1.50 |
| Royal Challengers Bangalore | 17 | 7.45 | 25 | 1.47 |
| Chennai Super Kings | 16 | 7.12 | 22 | 1.38 |
| Delhi Capitals | 15 | 7.38 | 20 | 1.33 |
| Rajasthan Royals | 14 | 7.54 | 19 | 1.36 |

---

## 💡 Actionable Recommendations

### For Team Management (Mumbai Indians)
1. **Maximize Deployment**: Bowl Bumrah in middle overs (best economy) AND death overs (most wickets)
2. **Risk Mitigation**: Avoid bowling to left-handed power hitters; deploy alternate bowlers
3. **Workload Planning**: Monitor performance clustering for early signs of fatigue
4. **Contract Value**: Career trajectory shows improvement → high retention priority

### For Opposition Teams
1. **Exploit Weakness**: Field left-handed batsmen when Bumrah bowls
2. **Strategic Timing**: Don't "wait out" Bumrah - he's effective in all phases
3. **Target Matchups**: Use proven performers like Gayle/Warner types
4. **Pitch Selection**: Choose batting-friendly surfaces when possible

---

## 🎓 Learning Outcomes

This project demonstrates:

### Data Science Skills
- ✅ Data extraction from complex JSON structures
- ✅ Feature engineering for machine learning
- ✅ Exploratory data analysis (EDA)
- ✅ Statistical hypothesis testing
- ✅ Time series trend analysis

### Machine Learning
- ✅ Unsupervised learning (K-Means clustering)
- ✅ Dimensionality reduction (PCA)
- ✅ Cluster validation (Silhouette Score)
- ✅ Feature standardization
- ✅ Model evaluation and interpretation

### Visualization
- ✅ Multi-panel dashboard creation
- ✅ Radar charts for multi-metric comparison
- ✅ Trend lines with annotations
- ✅ Professional infographic design
- ✅ Color-coded performance categories

### Domain Knowledge
- ✅ Cricket analytics and T20 strategy
- ✅ Performance metric interpretation
- ✅ Tactical insights generation
- ✅ Business intelligence reporting

---

## 📝 Notebook Structure

```
JB.ipynb
│
├── 1. Introduction & Objectives
│   └── Analysis goals and data source
│
├── 2. Data Extraction
│   ├── Import libraries
│   ├── Extract from 277 JSON files
│   ├── Parse deliveries for JJ Bumrah
│   └── Create structured DataFrame
│
├── 3. Exploratory Data Analysis
│   ├── Data summary statistics
│   ├── Phase distribution
│   ├── Opponent distribution
│   └── Sample data inspection
│
├── 4. Phase-wise Analysis
│   ├── Calculate metrics per phase
│   ├── Economy, dot %, strike rate
│   └── Visualization: 4-panel chart
│
├── 5. Dismissal Type Analysis
│   ├── Distribution of wicket types
│   ├── Percentage breakdown
│   └── Tactical interpretation
│
├── 6. Matchup Analysis
│   ├── Batting position analysis
│   ├── Head-to-head vs batsmen
│   ├── Performance vs teams
│   └── Insights and patterns
│
├── 7. Career Trend Analysis
│   ├── Year-over-year metrics
│   ├── Trend identification
│   ├── Peak years analysis
│   └── Improvement trajectory
│
├── 8. Visualization Suite
│   ├── Comprehensive 4-panel chart
│   ├── Phase-wise comparisons
│   ├── Career trend lines
│   └── Radar charts
│
├── 9. Machine Learning Analysis
│   ├── Feature engineering (14 metrics)
│   ├── Optimal K selection (Elbow + Silhouette)
│   ├── K-Means clustering (k=3)
│   ├── Cluster interpretation
│   ├── PCA visualization
│   └── Pattern analysis
│
├── 10. Comprehensive Conclusions
│   ├── Synthesis of all findings
│   ├── Visualization-based insights
│   ├── Key tactical insight
│   ├── Predictive framework
│   └── Data-driven recommendations
│
└── 11. Summary Infographic
    └── 7-panel dashboard with all key metrics
```

---

## 🏆 Final Verdict

### Overall Rating: ⭐⭐⭐⭐⭐ (5/5)

**JJ Bumrah is a WORLD-CLASS T20 BOWLER**

Based on 12+ years of data-driven analysis:
- ✅ Top 5 T20 bowler globally
- ✅ Elite performance across ALL metrics
- ✅ Continuous improvement trajectory
- ✅ Match-winning death overs capability
- ✅ Unique all-phase effectiveness

**One exploitable weakness**: Left-handed power hitters (Gayle, Warner, Dhawan)

---

## 👤 Author

**Soumya Ranjan Nayak**

- 🔗 LinkedIn: [soumya-ranjan-nayak-16855b247](https://www.linkedin.com/in/soumya-ranjan-nayak-16855b247/)
- 💻 GitHub: [amthesrn](https://github.com/amthesrn)
- 📄 Resume: [Google Drive](https://drive.google.com/file/d/1NS8J159r1WWpgqd_GVS6stfRwiVuoN9M/view?usp=drive_link)

### Cricket Background
- Represented Under-16 District team (Jharsuguda, Odisha)
- Regional Cricket: Kendriya Vidyalaya Jharsuguda (Ranchi Region)
- Inter-University Cricket: Symbiosis International University (Pune)
- Currently preparing for district matches (Open Category, Jharsuguda)

---

## 📚 References

1. **Cricsheet** - https://cricsheet.org/
   - Open cricket data in JSON format
   - Match-by-match ball-by-ball data

2. **scikit-learn Documentation** - https://scikit-learn.org/
   - K-Means clustering
   - PCA implementation
   - StandardScaler

3. **Matplotlib/Seaborn** - Visualization libraries
   - Professional plotting
   - Statistical visualizations

---

## 📄 License

This project uses open data from Cricsheet. The analysis and code are provided for educational and analytical purposes.

---

## 🤝 Contributing

Suggestions and improvements are welcome! Areas for enhancement:

1. **Additional ML Models**: Prophet for time series forecasting, XGBoost for feature importance
2. **Venue Analysis**: Home vs Away, ground-specific patterns
3. **Match Context**: Performance in wins vs losses, defending vs chasing
4. **Comparison Analysis**: Bumrah vs other elite T20 bowlers
5. **Interactive Dashboard**: Streamlit/Plotly for interactive exploration

---

## 📞 Contact

For questions, suggestions, or collaboration:
- LinkedIn: [soumya-ranjan-nayak-16855b247](https://www.linkedin.com/in/soumya-ranjan-nayak-16855b247/)
- GitHub: [amthesrn](https://github.com/amthesrn)

---

## ⭐ Acknowledgments

- **Cricsheet** for providing comprehensive cricket data
- **Mumbai Indians** for an incredible bowler
- **JJ Bumrah** for being an inspiration to cricket analytics enthusiasts

---

<div align="center">

**Made with ❤️ and Data**

*"In data we trust, in Bumrah we believe"*

</div>

---

## 🔄 Version History

- **v1.0** (2025-01-XX) - Initial comprehensive analysis
  - Data extraction from 277 matches
  - Statistical analysis complete
  - ML clustering implemented
  - Comprehensive visualizations
  - Data-driven conclusions

---

## 📊 Quick Stats Summary

```
╔══════════════════════════════════════════════════════════╗
║         JJ BUMRAH - CAREER HIGHLIGHTS                    ║
╠══════════════════════════════════════════════════════════╣
║  Matches Analyzed          │  145                        ║
║  Total Deliveries          │  3,474                      ║
║  Total Wickets             │  203                        ║
║  Overall Economy           │  7.19                       ║
║  Strike Rate               │  17.11 balls/wicket         ║
║  Dot Ball Percentage       │  39.7%                      ║
╠══════════════════════════════════════════════════════════╣
║  Best Phase                │  Middle Overs (6.59 eco)    ║
║  Most Wickets Phase        │  Death Overs (98 wickets)   ║
║  Best Year                 │  2024 (6.24 economy)        ║
║  Career Trajectory         │  IMPROVING ↗                ║
╠══════════════════════════════════════════════════════════╣
║  Biggest Bunny             │  R Pant (7W in 48 balls)    ║
║  Toughest Opponent         │  C Gayle (0W in 53 balls)   ║
║  Most Common Dismissal     │  Caught (57.6%)             ║
║  Signature Ball            │  Yorker (23% bowled)        ║
╚══════════════════════════════════════════════════════════╝
```

---

**Last Updated**: January 2025  
**Analysis Period**: 2013-2025 (12+ years)  
**Data Points**: 3,474 deliveries analyzed  
**Notebook Cells**: 34 cells (Code + Markdown)  
**Visualizations**: 9 comprehensive charts  
**ML Models**: K-Means clustering with PCA

---

