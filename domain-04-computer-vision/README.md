# Domain 04 — Computer Vision Solutions

> **Exam Weight:** 15-20% (Bobby says 15-20%, official guide says 10-15%)  
> **Bobby Russell Episode:** 4  
> **Study Days:** 36-38 (Phase 2, Week 8)

---

## ⚠️ Bobby Russell Says

> "This group accounts for about 15 to 20% of your exam."  
> Slightly higher than the official guide (10-15%). Take this seriously.

---

## 📋 Topics in This Domain

| File | Topic | Study Day |
|------|-------|-----------|
| `01_image_analysis.md` | Azure Vision API, tags, captions, OCR, smart crops | Day 36 |
| `02_ocr_face.md` | Read API (OCR), Face API, synchronous API | Day 37 |
| `03_custom_vision.md` | Classification, Object Detection, domains, training | Day 37 |
| `04_video_analysis.md` | Video Indexer, Spatial Analysis, GPT-4V | Day 38 |

---

## 🧠 Service Selection — Vision (CRITICAL)

| Need | Service |
|------|---------|
| Tags, captions, objects in a photo | **Azure Vision — Image Analysis** |
| Extract text from image or document | **Azure Vision — Read API (OCR)** |
| Detect, verify, or identify faces | **Azure Face API** |
| Your own custom image categories | **Custom Vision — Classification** |
| Find objects AND where they are | **Custom Vision — Object Detection** |
| Insights from video content | **Video Indexer** |
| People counting and movement in video | **Spatial Analysis** |
| Multimodal text and image analysis | **GPT-4V (Azure OpenAI)** |

---

## 🖼️ Image Analysis Features

> **Bobby says:** "You will need to know about capabilities like extracting text,
> detecting objects and people, generating captions and descriptions,
> suggesting smart crops and tags."

| Feature | What It Returns | Exam Keyword |
|---------|----------------|--------------|
| **Tags** | Labels with confidence scores | "label visual features" |
| **Caption** | Natural language description of image | "generate captions" |
| **Objects** | Object names and bounding boxes | "detect objects" |
| **Brands** | Recognized logos and brands | "detect brands" |
| **Color** | Dominant colors, accent color, B&W flag | "detect color schemes" |
| **Faces** | Face detection only — not identification | "detect people" |
| **Categories** | High-level image categories | "categorize image" |
| **Smart Crop** | Suggests best crop area | "area of interest" |
| **OCR / Read** | Extract text from images | "read text" |
| **Background Removal** | Remove image background | "background removal" |
| **Image Retrieval** | Find similar images | "image retrieval" |
| **Model Customization** | Train on your own images | "custom model" |

### How to Provide an Image — 3 Ways (memorize)

| Method | Example | When to Use |
|--------|---------|-------------|
| **File name on disk** | `"C:/images/photo.jpg"` | Local development |
| **Publicly accessible URL** | `"https://example.com/photo.jpg"` | Web images |
| **Binary data (byte stream)** | Raw bytes from file | Programmatic upload |

> **Exam pattern:**
> "Analyze image from a website URL. Which input method?"
> ✅ Publicly accessible URL
> ❌ Must upload to Azure Storage first — WRONG, URL works directly

---

## 📝 OCR — Read API

> **Bobby says:** "Focus on understanding how the synchronous API works,
> especially for OCR tasks in non-document images."

| Property | Detail |
|----------|--------|
| **Handles** | Printed text, handwriting, mixed content |
| **Best for** | Documents, forms, street signs, screenshots |
| **Returns** | Text lines, words, bounding polygons, confidence scores |
| **API type** | Synchronous — result returned immediately |

> **Key distinction (exam trap):**

| Use This | When |
|----------|------|
| **Read API** | Documents and non-document images with text |
| **Image Analysis** | Photos and scenes — objects, captions, tags |

### Setup Steps Bobby Says to Know

| Step | Action |
|------|--------|
| 1 | Locate your keys and endpoint |
| 2 | Set up your environment |
| 3 | Run the application |
| 4 | Analyze images and review output |

---

## 👤 Face API — 3 Operations

| Operation | What It Does | Use Case |
|-----------|-------------|----------|
| **Detection** | Find faces and return attributes | Count people in image |
| **Verification** | Are these two faces the same person? | Login, identity check |
| **Identification** | Who IS this person? Match against a group | Security access |

---

## 🎓 Custom Vision — Classification vs Detection

| Property | Image Classification | Object Detection |
|----------|---------------------|------------------|
| **Question asked** | What IS this image? | WHERE are the things? |
| **Output** | Single label for whole image | Labels and bounding boxes |
| **Training data needed** | Labeled images | Labeled images and drawn boxes |
| **Example output** | `"This is a cat"` | `"Cat at [x:120, y:45, w:200, h:180]"` |

---

## 🌍 Custom Vision Domains

> **Bobby says:** "Know the domains supported: generic, compact,
> landmarks, food, and retail. Know what is covered in each."

| Domain | Best For | Key Feature |
|--------|----------|-------------|
| **Generic** | Any general images | Most flexible, largest model |
| **Compact** | Mobile and edge deployment | Smaller model size, exportable |
| **Landmarks** | Famous locations and buildings | Geography recognition |
| **Food** | Food and dishes | Restaurant and delivery apps |
| **Retail** | Products on shelves | Inventory management |

> **Exam pattern:**
> "Deploy Custom Vision model to a mobile phone. Which domain?"
> ✅ Compact — designed for edge and mobile
> ❌ Generic — too large for mobile devices

---

## 🔄 Custom Vision Training Workflow

> **Bobby says:** "Know the steps in order from adding an image,
> adding tags, clicking done, and finally training your model."

```
Step 1 → Create project
          Name it, select classification type, choose domain

Step 2 → Upload images
          Add images to the project

Step 3 → Add tags
          Tag each image with the correct label
          Click DONE when finished tagging

Step 4 → Train the model
          Choose Quick Training or Advanced Training
          Process takes a few minutes

Step 5 → Evaluate results
          Review Precision, Recall, mAP
          Check probability and overlap thresholds
          If good → continue. If not → add images and retrain.

Step 6 → Publish the iteration
          Performance tab → model name + prediction resource

Step 7 → Consume the model
          Call prediction endpoint with new images
          Review results visually
          Use failed results for further training
```

---

## ⚡ Quick vs Advanced Training

| Property | Quick Training | Advanced Training |
|----------|---------------|------------------|
| **Speed** | Fast — minutes | Slower |
| **Control** | Automatic settings | More configuration options |
| **Best for** | Initial testing and prototyping | Production models |
| **Resource usage** | Lower | Higher |

---

## 📊 Custom Vision Metrics

> **Bobby says:** "Be familiar with how to interpret metrics like
> precision, recall, mean average precision, probability threshold,
> and overlapping thresholds."

| Metric | Simple Explanation | Good Value |
|--------|--------------------|------------|
| **Precision** | Of what I predicted positive, how many were actually right? | Higher = better |
| **Recall** | Of all actual positives, how many did I find? | Higher = better |
| **mAP** (mean Average Precision) | Overall model performance score | Higher = better |
| **Probability threshold** | Minimum confidence score to count as a detection | Adjustable |
| **Overlap threshold** | How much bounding boxes must overlap to count as correct | Adjustable — object detection only |

---

## 🛡️ Preventing Overfitting

> **Bobby says:** "Preventing overfitting and using a balanced
> and varied data set."

| Problem | Overfitting |
|---------|-------------|
| **What it is** | Model memorizes training images instead of learning patterns |
| **Symptom** | Great on training images, terrible on new images |
| **Example** | 99% training accuracy, 60% on new images |

| Prevention Strategy | How |
|--------------------|-----|
| **Balanced dataset** | Similar number of images per category |
| **Varied dataset** | Different angles, lighting, backgrounds |
| **Visual review** | Review prediction results visually |
| **Iterative training** | Use failed predictions as new training data |

---

## 💻 Code-First Approach — Python SDK Steps

> **Bobby says:** "Build a Custom Vision model using code-first
> approaches like Python SDK or REST API."

```python
# Step 1 — Create project
trainer.create_project(
    name="MyProject",
    domain_id=domain.id
)

# Step 2 — Add tags
tag = trainer.create_tag(project.id, "cat")

# Step 3 — Upload and label images
trainer.create_images_from_urls(
    project.id,
    images=[ImageUrlCreateEntry(url=url, tag_ids=[tag.id])]
)

# Step 4 — Train the model
iteration = trainer.train_project(project.id)

# Step 5 — Publish the model
trainer.publish_iteration(
    project.id,
    iteration.id,
    "MyModel",
    prediction_resource_id
)

# Step 6 — Test the prediction endpoint
predictor.classify_image_url(project.id, "MyModel", url)
```

> You do not need to run this code.
> Study what each step does and in what order.

---

## 🎥 Video Indexer

> **Bobby says:** "Azure AI Video Indexer runs over 30 AI models
> to generate insights from video or live stream."

| Insight Type | What It Extracts | Example |
|--------------|-----------------|---------|
| **Transcripts** | Speech converted to text | Full spoken content of a lecture |
| **OCR** | Text shown on screen in video frames | Slides, signs, captions visible in video |
| **Faces** | Face identification across video | "CEO appears at 02:14 and 15:30" |
| **Topics** | Main subjects discussed | "Video is about Azure AI and machine learning" |
| **Emotions** | Sentiment detected in speech and face | "Speaker is positive at 80% of video" |
| **Scene segmentation** | Different scenes identified | "Scene changes at 01:20, 04:45, 09:10" |
| **Named entities** | People, places, organizations mentioned | "Microsoft, Satya Nadella, Seattle" |
| **Keywords** | Important words and phrases | "AI, cloud, deployment, security" |

| Property | Detail |
|----------|--------|
| **Number of AI models** | 30+ running simultaneously |
| **Works on** | Video files AND live streams |
| **Access via** | Azure AI Foundry Tools |
| **Output format** | JSON with timestamps |

> **Exam pattern:**
> "Extract topics and speaker transcripts from a recorded conference.
> Which service?"
> ✅ Video Indexer — extracts insights from video
> ❌ Spatial Analysis — that monitors people movement, not content

---

## 👥 Spatial Analysis

> **Bobby says:** "Understand how people counting works in defined
> zones and how entrance counting tracks movements through doorways.
> The system can monitor social distancing and detect face masks."

| Feature | What It Does | Example Use Case |
|---------|-------------|-----------------|
| **People counting** | Count people present in defined zones | Store occupancy limit enforcement |
| **Entrance counting** | Track movement through doorways | Building entry and exit logging |
| **Social distancing** | Monitor distance between people | COVID compliance monitoring |
| **Face mask detection** | Detect if people are wearing masks | Safety compliance in workplace |

| Property | Detail |
|----------|--------|
| **Works on** | Live video feeds — not static images |
| **Defines** | Custom zones and doorways in the camera view |
| **Output** | Real-time events and counts |

> **Exam pattern:**
> "Count customers entering a store through the main entrance.
> Which service?"
> ✅ Spatial Analysis — entrance counting
> ❌ Video Indexer — that extracts content insights, not movement

---

## 🧠 Memory Palace — The Vision Department

**Building 7 in your Robot Factory Town:**

```
🔭 BUILDING 7: THE VISION DEPARTMENT

┌─────────────────────────────────────────┐
│  FLOOR 3 — SURVEILLANCE ROOM            │
│  🎥 Live camera feeds everywhere        │
│  4 monitors:                            │
│    👥 PEOPLE COUNT                      │
│    🚪 ENTRANCE TRACKING                 │
│    📏 DISTANCE MONITORING               │
│    😷 MASK DETECTION                    │
├─────────────────────────────────────────┤
│  FLOOR 2 — VIDEO ANALYSIS ROOM          │
│  30+ TV screens running AI models       │
│  Screens show faces, text, scenes,      │
│  emotions, topics all at once           │
│  Live feed camera in the corner         │
├─────────────────────────────────────────┤
│  FLOOR 1 — CUSTOM VISION STUDIO         │
│  5 doors: GENERIC COMPACT LANDMARKS     │
│           FOOD    RETAIL                │
│  Assembly line:                         │
│  UPLOAD→TAG→DONE→TRAIN→EVALUATE→PUBLISH │
│  Two machines: QUICK and ADVANCED       │
│  Report card: Precision, Recall, mAP    │
├─────────────────────────────────────────┤
│  GROUND FLOOR — IMAGE ANALYSIS LAB      │
│  Giant eye 👁️ looking at photos         │
│  Returns: Tags, Captions, Objects,      │
│           Brands, Colors, Smart Crops   │
│  3 input slots on wall:                 │
│    [FILE NAME] [URL LINK] [BYTE STREAM] │
└─────────────────────────────────────────┘
```

---

## 🎯 Exam Priority Checklist

### Must Know

- [ ] Image Analysis features — full table
- [ ] 3 ways to provide image input — file, URL, binary
- [ ] Read API = OCR for documents and non-document images
- [ ] Face API 3 operations — detection, verification, identification
- [ ] Classification vs Object Detection — question asked and output
- [ ] Training steps in exact order — Upload → Tag → Done → Train → Evaluate → Publish → Test
- [ ] Training metrics — Precision, Recall, mAP

### Should Know

- [ ] 5 Custom Vision domains — Generic, Compact, Landmarks, Food, Retail
- [ ] Compact domain = mobile and edge deployment
- [ ] Quick vs Advanced training differences
- [ ] Overfitting prevention — balanced and varied dataset
- [ ] Video Indexer runs 30+ AI models simultaneously
- [ ] Spatial Analysis 4 features — people count, entrance, distancing, masks

### Good to Know

- [ ] Code-first approach steps using Python SDK
- [ ] Probability threshold and overlap threshold
- [ ] Background removal and image retrieval features
- [ ] Live stream support in Video Indexer

---

## ❓ Quick Self-Test

**Q1. Name 4 things Image Analysis can return from a photo.**

<details>
<summary>▶ Click to reveal answer</summary>

Any 4 from this list:

| Feature | Returns |
|---------|---------|
| Tags | Labels with confidence scores |
| Caption | Natural language description |
| Objects | Names and bounding boxes |
| Brands | Recognized logos |
| Color | Dominant colors |
| Smart Crop | Best crop suggestion |
| Background Removal | Image without background |

</details>

---

**Q2. How many ways can you provide an image to the Vision API?
What are they?**

<details>
<summary>▶ Click to reveal answer</summary>

**3 ways:**

| Method | Example |
|--------|---------|
| File name on disk | `"C:/photo.jpg"` |
| Publicly accessible URL | `"https://example.com/photo.jpg"` |
| Binary data byte stream | Raw bytes from file |

</details>

---

**Q3. Custom Vision model needs to run on a mobile phone.
Which domain?**

<details>
<summary>▶ Click to reveal answer</summary>

**Compact**

| Domain | Use Case |
|--------|----------|
| Generic | General images — flexible |
| **Compact** | **Mobile and edge — small size** |
| Landmarks | Famous locations |
| Food | Dishes and meals |
| Retail | Products on shelves |

</details>

---

**Q4. What are the Custom Vision training steps in order?**

<details>
<summary>▶ Click to reveal answer</summary>

| Step | Action |
|------|--------|
| 1 | Upload images |
| 2 | Add tags — click Done |
| 3 | Train — Quick or Advanced |
| 4 | Evaluate — Precision, Recall, mAP |
| 5 | Publish iteration |
| 6 | Test prediction endpoint |

</details>

---

**Q5. Model gets 99% on training images but fails on new images.
What is the problem and how do you fix it?**

<details>
<summary>▶ Click to reveal answer</summary>

| | Detail |
|-|--------|
| **Problem** | Overfitting — memorized training data |
| **Symptom** | Great on training, bad on new images |
| **Fix 1** | Add more images — balanced per category |
| **Fix 2** | Add variety — different angles, lighting |
| **Fix 3** | Use failed predictions as new training data |

</details>

---

**Q6. Video Indexer vs Spatial Analysis — what is the difference?**

<details>
<summary>▶ Click to reveal answer</summary>

| Property | Video Indexer | Spatial Analysis |
|----------|--------------|-----------------|
| **Purpose** | Extract insights from video content | Monitor people movement in space |
| **Good for** | "What is IN this video?" | "What are PEOPLE DOING here?" |
| **Output** | Transcripts, faces, topics, emotions | Counts, zone events, alerts |
| **AI models** | 30+ simultaneously | Focused on people detection |
| **Works on** | Video files and live streams | Live video feeds |

</details>

---

**Q7. Difference between Image Classification and Object Detection?**

<details>
<summary>▶ Click to reveal answer</summary>

| Property | Image Classification | Object Detection |
|----------|---------------------|-----------------|
| **Question** | What IS this image? | WHERE are the things? |
| **Output** | One label for whole image | Labels and bounding boxes |
| **Example** | "This is a cat" | "Cat at [x:120, y:45]" |

</details>

---

*Domain 04 — Merged: Bobby Russell Episode 4 and technical reference*  
*Part of the AI-102 study repository*