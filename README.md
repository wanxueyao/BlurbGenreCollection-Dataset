# BlurbGenreCollection-Dataset (Reformatted)

A research-friendly reformatted version of the original **BlurbGenreCollection-EN** dataset for hierarchical multi-label text classification (HMTC).

## 📖 About This Repository

This repository provides a **reformatted version** of the excellent [BlurbGenreCollection-EN](https://www.inf.uni-hamburg.de/en/inst/ab/lt/resources/data/blurb-genre-collection.html) dataset created by the Language Technology Group at Universität Hamburg. 

The original dataset is of exceptional quality and has been widely used in HMTC research. However, we found that its XML-based format can be somewhat cumbersome to load and parse for quick experimentation. To facilitate easier access for the research community, we have performed minimal reformatting—converting the data into simple CSV files while preserving all original information.

> **Important**: This is not a new dataset. We have merely changed the format for convenience. All credit for the dataset's creation, curation, and quality belongs to the original authors. Please cite the original work according to their guidelines (see [Citation](#citation) below).

## 📊 Dataset Statistics

| Split | Samples |
|-------|---------|
| Train | 58,715 |
| Dev (Validation) | 14,785 |
| Test | 18,394 |
| **Total** | **91,894** |

**Hierarchy Structure:**
- **Total Labels**: 152 genres organized in a hierarchical taxonomy
- **Maximum Depth**: 4 levels
- **Top-level Categories**: 8 (Nonfiction, Fiction, Classics, Children's Books, Teen & Young Adult, Humor, Poetry)

## 📁 Repository Structure

```
BlurbGenreCollection-Dataset/
├── bgc_train.csv          # Reformatted training set
├── bgc_dev.csv            # Reformatted development/validation set
├── bgc_test.csv           # Reformatted test set
├── hiearchy.json          # Label hierarchy as nested JSON (easy to parse)
├── README.md              # This file
└── blurbgenrecollectionen/    # Original dataset files
    ├── BlurbGenreCollection_EN_train.txt
    ├── BlurbGenreCollection_EN_dev.txt
    ├── BlurbGenreCollection_EN_test.txt
    ├── hierarchy.txt      # Original hierarchy format
    ├── description.pdf    # Original dataset documentation
    └── README.txt         # Original README
```

## 📋 Data Format

### CSV Files (`bgc_*.csv`)

Each CSV file contains the following columns:

| Column | Description |
|--------|-------------|
| `Number` | Sample index |
| `Title` | Book title |
| `Body` | Blurb text (advertising description of the book) |
| `Topics` | Hierarchical labels in path format (e.g., `Fiction>Mystery & Suspense>Crime Mysteries`) |

**Example:**
```csv
Number,Title,Body,Topics
1,"The New York Times Daily Crossword Puzzles...","Monday's Crosswords Do with Ease...",Nonfiction>Games
2,"Creatures of the Night","Two of literary comics modern masters...",Fiction>Graphic Novels & Manga
```

### Hierarchy File (`hiearchy.json`)

The label hierarchy is provided as a nested JSON object for easy programmatic access:

```json
{
  "Nonfiction": {
    "Biography & Memoir": {
      "Arts & Entertainment Biographies & Memoirs": {},
      "Political Figure Biographies & Memoirs": {},
      ...
    },
    ...
  },
  "Fiction": { ... },
  ...
}
```

## 🔗 Related Resources

### 📁 RCV1 Dataset (Reformatted)

We have also prepared a similarly reformatted version of the classic **Reuters Corpus Volume I (RCV1)** dataset. Like BGC, RCV1 is a high-quality, large-scale hierarchical text classification benchmark that has stood the test of time.

> 🔗 Link: https://github.com/wanxueyao/RCV1-Dataset

### 🤖 LLM-based HMTC Methods — *Work in Progress!*

Excited about hierarchical multi-label text classification? So are we! 

We're cooking up some fresh LLM-based approaches for HMTC on these two legendary datasets. Large language models meet classic benchmarks — what could go wrong? (Famous last words... 😅)

> 🔗 Link: *Coming soon — stay curious!*

## 📜 Original Dataset Description

The BlurbGenreCollection-EN consists of advertising descriptions (blurbs) of books in English. Each blurb is categorized into one or multiple genre categories organized in a hierarchical structure.

Key properties (following RCV1 policies):
- **Minimum Code Policy**: Every document is assigned at least one category
- **Hierarchy Policy**: All ancestors of assigned labels are also assigned

Copyright of blurbs belongs to Penguin Random House (PRH). Permission has been granted to share this dataset for research purposes under the [CC BY-NC 4.0 license](https://creativecommons.org/licenses/by-nc/4.0/).

## 📚 Citation

If you use this dataset, please cite the original work as specified by the authors:

```bibtex
@inproceedings{aly-etal-2019-hierarchical,
    title = "Hierarchical Multi-label Classification of Text with Capsule Networks",
    author = "Aly, Rami  and
      Remus, Steffen  and
      Biemann, Chris",
    booktitle = "Proceedings of the 57th Annual Meeting of the Association for Computational Linguistics: Student Research Workshop",
    month = jul,
    year = "2019",
    address = "Florence, Italy",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/P19-2045",
    doi = "10.18653/v1/P19-2045",
    pages = "323--330",
}
```

For more information about the original dataset, please visit:  
🔗 https://www.inf.uni-hamburg.de/en/inst/ab/lt/resources/data/blurb-genre-collection.html

## 📧 Contact

For questions regarding **this reformatted version**, please open an issue in this repository.

For questions about **the original dataset**, please contact the original authors as specified in their documentation.

---

*This reformatted version is provided to facilitate research. We are grateful to the original authors for creating and sharing this valuable resource with the community.*
