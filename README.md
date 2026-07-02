# misc
Qwen3-ASRの qwen-asr-serve（vllm-0.14.0のOpenAI互換APIサーバ）の出力を書き換えるパッチを2つつくりました．
目的にあわせて選んで使ってください．

## (1) vllm_qwen3_asr_strip_prefix.patch ##
Qwen3-ASRの qwen-asr-serve（vllm-0.14.0のOpenAI互換APIサーバ）の出力から言語プリフィックス（"language Japanese<asr_text>"のような記述）を除去するためのパッチ
```
$ wget -P /tmp https://raw.githubusercontent.com/takago/misc/refs/heads/main/vllm_qwen3_asr_strip_prefix.patch
$ cd ${HOME}/miniconda3/envs/qwen3-asr/lib/python3.12/site-packages/
$ patch -p0 < /tmp/vllm_qwen3_asr_strip_prefix.patch
```
ワンライナーでやるなら
```
$ conda activate qwen3-asr
(qwen3-asr)$ wget -qO- https://raw.githubusercontent.com/takago/misc/refs/heads/main/vllm_qwen3_asr_strip_prefix.patch | patch -p0 -d "$(python -c 'import site; print(site.getsitepackages()[0])')"
```

## (2) vllm-qwen3-asr-language-filter.patch ##
Qwen3-ASRの qwen-asr-serve（vllm-0.14.0のOpenAI互換APIサーバ）の出力から，指定言語以外の部分を削除するためのパッチ
```
$ wget -P /tmp https://raw.githubusercontent.com/takago/misc/refs/heads/main/vllm-qwen3-asr-language-filter.patch
$ cd ${HOME}/miniconda3/envs/qwen3-asr/lib/python3.12/site-packages/
$ patch -p0 < /tmp/vllm-qwen3-asr-language-filter.patch
```
ワンライナーでやるなら
```
$ conda activate qwen3-asr
(qwen3-asr)$ wget -qO- https://raw.githubusercontent.com/takago/misc/refs/heads/main/vllm-qwen3-asr-language-filter.patch | patch -p0 -d "$(python -c 'import site; print(site.getsitepackages()[0])')"
```
