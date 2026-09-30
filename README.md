<img src="sdcv.png">

# What is sdcv?

Interface for sdcv (StartDict console version).

Translate word by sdcv (console version of Stardict), and display
translation use posframe or buffer.

## Installation

#### 1. Install Stardict and sdcv

To use this extension, you have to install Stardict and sdcv

##### Linux
```Bash
sudo aptitude install stardict sdcv -y
```

##### MacOS
```Bash
brew install stardict sdcv
```

##### Windows (MSYS2 UCRT64)
Run the following command in the MSYS2 UCRT64 terminal:
```Bash
pacman -S mingw-w64-ucrt-x86_64-sdcv
```

#### 2. Configure with use-package and straight.el

Add the following to your Emacs configuration. Replace the dictionary directory
with the path to your installed dictionaries.

```Elisp
(use-package posframe
  :straight (:host github :repo "tumashu/posframe"))

(use-package sdcv
  :straight (:host github :repo "donaldsdlo/sdcv")
  :bind (("C-x y" . sdcv-search-pointer+))
  :custom
  (sdcv-say-word-p t)
  (sdcv-dictionary-data-dir "startdict_dictionary_directory")
  (sdcv-dictionary-simple-list
   '("懒虫简明英汉词典"
     "懒虫简明汉英词典"
     "KDic11万英汉词典"))
  (sdcv-dictionary-complete-list
   '("懒虫简明英汉词典"
     "英汉汉英专业词典"
     "XDICT英汉辞典"
     "stardict1.3英汉辞典"
     "WordNet"
     "XDICT汉英辞典"
     "Jargon"
     "懒虫简明汉英词典"
     "FOLDOC"
     "新世纪英汉科技大词典"
     "KDic11万英汉词典"
     "朗道汉英字典5.0"
     "CDICT5英汉辞典"
     "新世纪汉英科技大词典"
     "牛津英汉双解美化版"
     "21世纪双语科技词典"
     "quick_eng-zh_CN")))
```

After completing the above configuration, please execute the command ```sdcv-check```
to confirm that the dictionary settings is correct,
otherwise sdcv will not work because there is no dictionary file in sdcv-dictionary-data-dir.

## Usage

Below are commands you can use:

| Command              | Description                                  |
| :---                 | :---                                         |
| sdcv-search-pointer  | Search around word and display with buffer.  |
| sdcv-search-pointer+ | Search around word and display with tooltip. |
| sdcv-search-input    | Search input word and display with buffer.   |
| sdcv-search-input+   | Search input word and display with tooltip.  |

Tips:

If current mark is active, sdcv commands will translate
region string, otherwise translate word around point.

## Dictionary
You can download sdcv dictionary from http://download.huzheng.org/dict.org/
