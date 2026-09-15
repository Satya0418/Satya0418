<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0891b2&height=120&section=header&text=&fontSize=0" width="100%"/>

# Satyaprakash Yadav

**Backend & AI Systems Engineer**

*I build systems that extract, structure, and serve real-world data —*  
*from regulatory documents to handwritten pages.*

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0891b2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/your-linkedin)
[![Email](https://img.shields.io/badge/Email-0d1117?style=for-the-badge&logo=gmail&logoColor=0891b2)](mailto:your@email.com)
[![GitHub](https://img.shields.io/badge/GitHub-0d1117?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Satya0418)

</div>

---

## What I Build

Every system I've built follows the same pattern: take messy, unstructured, or distributed data and turn it into something queryable, structured, and useful.

```
RAW DATA SOURCE          EXTRACTION               INTELLIGENCE
(5 regulatory portals,   (async crawlers,         (normalization,
 handwritten pages,       OCR pipelines,           change detection,
 product catalogs)        PDF parsers)             ML inference)
        |                      |                        |
        └──────────────────────┴────────────────────────┘
                                        |
                               BACKEND API (FastAPI / Django)
                                        |
                               USER / EXPORT / UI
```

<br/>

<div align="center">

| 🔍 Data Extraction | 🤖 Applied ML | ⚙️ Backend APIs | 📊 Data Systems |
|:---:|:---:|:---:|:---:|
| Web crawlers | CRNN/CTC OCR | FastAPI | Normalization |
| PDF parsers | TensorFlow/Keras | Django REST | Change detection |
| Multi-source ingestion | OpenCV pipelines | asyncio | SQLite schemas |

</div>

---

## Flagship Systems

### 🏥 Medicine Safety Intelligence Platform
> Multi-authority pharmaceutical regulatory intelligence — built as a freelance system.

A backend that searches, crawls, and harmonizes drug safety data across **5 international regulatory authorities** simultaneously. When you search for a drug, the system fires 5 concurrent async scrapers, normalizes results through source-specific adapters, detects safety label revisions via SHA-256 hashing, and persists everything into a relational store.

```
Search: "Ozempic"
        |
FastAPI Orchestration Layer (app/api/drugs.py)
        |   asyncio.gather()
  ┌─────┴────────────────────────────────────────┐
  🇺🇸 FDA SrLC  🍁 Health Canada  🇦🇺 TGA  🚨 MedWatch  🇬🇧 MHRA
  └─────┬────────────────────────────────────────┘
        |   (per source)
Normalization Adapter → Change Detection (SHA-256 hash diff)
        |
SQLite: drugs + safety_labeling_changes tables
        |
REST API  ·  Web UI  ·  CSV / JSON Export
```

**What it handles:** Prescription labeling changes · Boxed Warnings · Adverse Reactions · Post-market surveillance · Class I/II/III recalls · UK MHRA bulletins · Canadian Drug Monographs

**Subsystem:** Separate FastAPI-based PDF extractor service with its own test suite, Docker config, and hierarchical section/table extraction.

**Stack:** `Python` `FastAPI` `asyncio` `SQLite` `BeautifulSoup` `pytest` `nginx` `systemd`

[![Repository](https://img.shields.io/badge/Repository-0891b2?style=flat-square&logo=github&logoColor=white)](https://github.com/Satya0418/webcrawler)

---

### ✍️ Parseon OCR Engine

A custom handwriting recognition system trained from scratch — no Tesseract, no Google Vision, no cloud APIs.

The engine trains a **CRNN (CNN + BiLSTM + CTC)** model on the IAM Handwritten Forms dataset. At inference, it uses OpenCV to detect text regions on a full page, crops each line, preprocesses to match training format, and runs the model per line before assembling the full page text.

```
Full-Page Handwritten Image
        |
OpenCV Text-Region Detection
(contour analysis → bounding boxes → line crops)
        |   per line
Preprocessing: resize → normalize → grayscale
        |
CRNN Inference:
  CNN (feature extraction)
    → BiLSTM (sequence modeling)
       → CTC Decoder (character recognition)
        |
Assembled Page Text
```

**Training:** Kaggle T4 GPU · IAM Forms Dataset · 60-epoch CRNN · character map generation

**Frontend:** React (Vite) interface for image upload and result display

**Stack:** `Python` `TensorFlow/Keras` `OpenCV` `NumPy` `CRNN` `CTC Loss` `Kaggle` `React` `Vite`

[![Repository](https://img.shields.io/badge/Repository-0891b2?style=flat-square&logo=github&logoColor=white)](https://github.com/Satya0418/parseon-ocr)

---

## Supporting Projects

<table>
<tr>
<td width="50%">

**🎓 Campus Connect**

Full LMS platform with three separate role dashboards (Student, Faculty, Admin). Custom AbstractUser model with role-based permissions. Course management, assignment submission, grading, communication.

`Django` `DRF` `JWT` `React` `SQLite`

[→ Repository](https://github.com/Satya0418/Campus_connect)

</td>
<td width="50%">

**📈 BizAnalytics – Sales Analyzer**

Full-stack analytics dashboard with JWT authentication. Seven Chart.js visualizations on a grocery sales dataset. Django backend serving templates and API. Three-page app: Landing, Login, Dashboard.

`Django` `JWT` `Chart.js` `Vanilla JS` `SQLite`

[→ Repository](https://github.com/Satya0418/Sales_Analyzer)

</td>
</tr>
<tr>
<td width="50%">

**🛍️ Product Compare**

Django product comparison platform. Category/Product ORM models, user authentication, image upload with ImageField, media file serving.

`Django` `SQLite` `Pillow`

[→ Repository](https://github.com/Satya0418/compare)

</td>
<td width="50%">

**🔗 React + Django Integration**

Full-stack boilerplate — Django REST Framework backend with DRF serializers, CORS handling, and a React/Vite frontend consuming the API.

`Django` `DRF` `React` `Vite`

[→ Repository](https://github.com/Satya0418/-react-new-django)

</td>
</tr>
</table>

---

## Tech Stack

Derived from what I've actually built.

**Languages**
```
Python (primary)    JavaScript (React frontends)
```

**AI / ML**
```
TensorFlow / Keras    OpenCV    CRNN architecture    CTC loss
IAM dataset    Kaggle GPU training pipelines
```

**Backend**
```
FastAPI    Django    Django REST Framework
asyncio    BeautifulSoup    requests
```

**Databases**
```
SQLite    Django ORM
```

**Infrastructure**
```
nginx    systemd    Docker    pytest    Linux deployment
```

**Frontend**
```
React    Vite    Chart.js    Vanilla JS
```

---

## GitHub Activity

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=Satya0418&show_icons=true&theme=github_dark&hide_border=true&title_color=0891b2&icon_color=38bdf8&text_color=e6edf3&bg_color=0d1117)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=Satya0418&layout=compact&theme=github_dark&hide_border=true&title_color=0891b2&text_color=e6edf3&bg_color=0d1117&langs_count=6)

</div>

---

## Connect

<div align="center">

If you're working on systems that need to extract intelligence from messy or distributed data sources — regulatory documents, handwritten records, multi-format pipelines — I'd be interested in talking.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0891b2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/your-linkedin)
[![Email](https://img.shields.io/badge/Email-Reach%20Out-0891b2?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your@email.com)

</div>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0891b2&height=80&section=footer" width="100%"/>
</div>
