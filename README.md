# 🤖 Teachable Machine

A lightweight, **zero-dependency** AI application that learns from user-provided text examples and classifies new inputs — all running entirely in the browser.
---

## ✨ Features

- **Train with your own data** — add any number of custom classes and text samples
- **Instant classification** — see confidence scores for every class in real time
- **No server, no backend** — runs 100% in the browser, no internet required after load
- **Zero dependencies** — pure HTML, CSS, and vanilla JavaScript in a single file
- **Rename & manage classes** — double-click any class name to rename it on the fly
- **Animated results** — smooth confidence bar animations for every prediction
- **Responsive design** — works on desktop and mobile

---

## 🚀 Getting Started

### Option 1 — Just open it
Download `teachable-machine.html` and open it directly in any modern browser. That's it.

```bash
# Clone the repo
git clone https://github.com/your-username/teachable-machine.git

# Open in browser
open teachable-machine.html
```

## 🧠 How It Works

### Training
1. Open the **🎓 Train** tab
2. Create classes (e.g. `Cat`, `Dog`, `Bird`) — rename by double-clicking
3. Add text descriptions as samples for each class
   - Example for **Cat**: *"furry animal that purrs and meows"*
   - Example for **Dog**: *"loyal pet that barks and fetches"*
4. Click **🚀 Train Model**

### Testing
1. Switch to the **🔍 Test** tab
2. Type any description in the input box
3. Click **⚡ Classify** to see predictions with confidence scores

### The Algorithm
The classifier uses a **token-overlap similarity** approach inspired by TF-IDF:

- Each input is tokenized into lowercase words
- Similarity between the input and each training sample is computed using Jaccard-style overlap, normalized by the geometric mean of token counts
- Per-class scores are the **max similarity** across all samples for that class
- Final confidence values are softmax-normalized across all classes

> The more descriptive and varied your training samples, the more accurate the classifications become.

---

## 🛠️ Customization

Want to extend it? Here are some quick starting points:

**Add default classes on load**
```javascript
let classes = [
  { id: 0, name: 'Positive', samples: [] },
  { id: 1, name: 'Negative', samples: [] },
  { id: 2, name: 'Neutral', samples: [] },
];
```

**Change the color palette**
```javascript
const COLORS = [
  { bg: '#your-color', light: '#...', dark: '#...', accent: '#...' },
  // add more...
];
```

**Swap in a smarter algorithm**
Replace the `similarity()` function with cosine similarity, BM25, or connect to an embedding API for production-grade accuracy.

---

## 🌐 Browser Support

| Browser | Support |
|---|---|
| Chrome / Edge | ✅ Full |
| Firefox | ✅ Full |
| Safari | ✅ Full |
| Mobile browsers | ✅ Full |

---

## 📄 License

MIT — free to use, modify, and distribute.

---

## 🙌 Contributing

Pull requests are welcome! Feel free to open an issue for bugs, ideas, or improvements.

1. Fork the repo
2. Create your branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

> Built with 💚 — no frameworks, no build tools, just the web platform.
