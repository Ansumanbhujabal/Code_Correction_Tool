```markdown
# HTML Fixer with T5 Transformer

An AI-powered tool for automatically correcting and improving HTML code using sequence-to-sequence transformers.

![HTML Validation](https://img.shields.io/badge/HTML-Valid-brightgreen) ![Python Version](https://img.shields.io/badge/Python-3.8%2B-blue) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Features

- 🛠️ Fixes common HTML errors (mismatched tags, improper nesting)
- 🎨 Converts inline styles to semantic classes
- ♿ Adds accessibility attributes automatically
- 📏 Improves code formatting and indentation
- 🔄 Handles case inconsistencies in tags
- ⚡ Powered by Google's T5 transformer model
- 📊 Built-in accuracy and speed evaluation

## Installation

```bash
pip install torch transformers beautifulsoup4 scikit-learn
```

## Usage

### Basic Correction
```python
from html_fixer import correct_html

bad_html = "<DIV CLASS='header'><img src='logo.jpg'></DIV>"
fixed_html = correct_html(bad_html)
print(fixed_html)
```

### Training the Model
```python
# Customize training parameters in the script
EPOCHS = 20
BATCH_SIZE = 4
MAX_LENGTH = 768  # For longer HTML documents

# Run training
if __name__ == "__main__":
    train_model()
```

## Key Components

### Model Architecture
- Base Model: `t5-small` (can be upgraded to `t5-base` or `t5-large`)
- Input Format: `fix html: [raw_html_input]`
- Output Format: Corrected HTML

### Validation Metrics
![Screenshot from 2025-01-31 14-11-18](https://github.com/user-attachments/assets/d2f3b71c-61a7-48c4-b795-4e0989b4543e)


*Depends on training data similarity  
**On CPU (Intel i7)

## Dataset Structure
```json
[
  {
    "bad_code": "<div class='CONTAINER'>...</div>",
    "good_code": "<div class=\"container\">...</div>"
  },
  ...
]
```

## Evaluation Results
Sample output from test cases:
```
Input: <SECTION><p>Text</p></SECTION>
Output: <section><p>Text</p></section>

Input: <img src="image.png">
Output: <img src="image.png" alt="description"/>
```

## Contributing

1. Fork the repository
2. Add new training examples to `data`
3. Improve post-processing rules
4. Submit a pull request

## License

MIT License - see [LICENSE](LICENSE) for details

## Future Improvements

- Add HTML5 semantic validation
- Support for CSS/JS cleanup
- Browser compatibility checks
- Interactive web interface

---

**Note**: For production use, consider:
- Using larger T5 variants (t5-base/t5-large)
- GPU acceleration
- Adding domain-specific training data
```
