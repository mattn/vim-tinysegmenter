# vim-tinysegmenter

Vim port of TinySegmenter - Super compact Japanese tokenizer.

http://chasen.org/~taku/software/TinySegmenter/

## Installation

Install with your favorite plugin manager. For example, using [vim-plug](https://github.com/junegunn/vim-plug):

```vim
Plug 'mattn/vim-tinysegmenter'
```

## Usage

### Instance-based usage (recommended for multiple instances)

```vim
" Create a new TinySegmenter instance
let ts = tinysegmenter#new()

" Set preserve words (optional)
let ts.preserve_list = ['東京都', '日本語']

" Segment Japanese text
echo ts.segment('私は日本語を勉強しています。')
" ['私', 'は', '日本語', 'を', '勉強', 'し', 'て', 'い', 'ます', '。']
```

### Simple function-based usage

```vim
" Segment with optional preserve list and token preservation
echo tinysegmenter#segment('私は東京都に住んでいます。', ['東京都'], 0)
```

## API

### `tinysegmenter#new()`
Creates a new TinySegmenter instance.

```vim
let ts = tinysegmenter#new()
```

### Instance methods

#### `segment(input)`
Segments the input text into words.

```vim
let ts = tinysegmenter#new()
let segments = ts.segment('私は学生です。')
```

#### `preserve_list` (property)
List of words to preserve during segmentation.

```vim
let ts = tinysegmenter#new()
let ts.preserve_list = ['東京都', '山田太郎']
```

#### `preserve_tokens` (property)
Whether to preserve tokens (alphanumeric sequences).

```vim
let ts = tinysegmenter#new()
let ts.preserve_tokens = 1
```

## License

Modified BSD License (same as original TinySegmenter)

## Original Implementation

- [TinySegmenter](http://chasen.org/~taku/software/TinySegmenter/) by Taku Kudo

## Author

Yasuhiro Matsumoto (a.k.a mattn)
