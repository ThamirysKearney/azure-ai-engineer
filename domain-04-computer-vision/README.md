# Domain 04 — Computer Vision Solutions

> **Exam Weight:** 10-15%
> **Bobby Russell Episode:** 4
> **Study Days:** 36-38 (Phase 2, Week 8)

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_image_analysis.md` | Azure Vision API, tags, captions, brands | Day 36 |
| `02_ocr_face.md` | Read API, Face API | Day 37 |
| `03_custom_vision.md` | Classification, Object Detection, training | Day 37 |
| `04_video_analysis.md` | Video Indexer, Spatial Analysis, GPT-4V | Day 38 |

---

## 🧠 Service Selection — Vision (CRITICAL)

| Need | Service |
|------|---------|
| Tags, captions, objects in a photo | **Azure Vision — Image Analysis** |
| Extract text from image/document | **Azure Vision — Read API (OCR)** |
| Detect/verify/identify faces | **Azure Face API** |
| YOUR custom image categories | **Custom Vision — Classification** |
| Find objects + WHERE they are | **Custom Vision — Object Detection** |
| Insights from video | **Video Indexer** |
| People counting/movement | **Spatial Analysis** |
| Multimodal text + image analysis | **GPT-4V (Azure OpenAI)** |

---

## 🖼️ Image Analysis Features

Bobby says:
> "Azure AI Vision is used to tag visual features, detect color schemes, detect domain-specific content, and detect brands. The Face API is used to verify identities."

| Feature | What it returns |
|---------|----------------|
| Tags | Labels with confidence scores |
| Caption | Natural language description |
| Objects | Object names + bounding boxes |
| Brands | Recognized logos/brands |
| Color | Dominant colors, accent color, B&W? |
| Faces | Face detection (not identification) |
| Categories | High-level image categories |

---

## 📝 OCR — Read API

- Handles: printed text + handwriting + mixed
- Best for: documents, forms, street signs, screenshots
- Returns: text lines, words, bounding polygons, confidence scores

> Use **Read API** for documents. Use **Image Analysis** for photos/scenes.

---

## 👤 Face API — 3 Operations

| Operation | What it does | Use case |
|-----------|-------------|----------|
| **Detection** | Find faces, return attributes | How many people in image? |
| **Verification** | Are these two faces the same person? | Login, identity check |
| **Identification** | Who IS this person? (from a group) | Security access |

---

## 🎓 Custom Vision — Classification vs Detection

| | Image Classification | Object Detection |
|--|---------------------|------------------|
| **Question** | What IS this image? | WHERE are things? |
| **Output** | Single label for whole image | Labels + bounding boxes |
| **Training** | Labeled images | Labeled images + drawn boxes |
| **Example** | "This is a cat" | "Cat at [x,y,w,h]" |

### Training Workflow
```
1. Create Custom Vision project
2. Upload labeled images
3. Train → creates an Iteration
4. Evaluate (precision, recall, mAP)
5. Publish iteration → get prediction endpoint
6. Call prediction API with new images
```

---

## 🎥 Video Indexer Capabilities

Extracts from video:
- Face identification
- OCR (text in video frames)
- Scene segmentation
- Topic detection
- Spoken language transcription
- Sentiment analysis
- Named entity extraction

---

*Domain 04 — Part of the AI-102 study repository*