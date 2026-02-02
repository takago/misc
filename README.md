# misc

## (1) vllm_qwen3_asr_strip_prefix.patch ##
Qwen3-ASRの qwen-asr-serve（vllm-0.14.0のOpenAI互換APIサーバ）の出力から言語プリフィックス（"language Japanese<asr_text>"のような記述）を除去するためのパッチ
```
$ wget -P /tmp https://raw.githubusercontent.com/takago/misc/refs/heads/main/vllm_qwen3_asr_strip_prefix.patch
$ cd ${HOME}/miniconda3/envs/qwen3-asr/lib/python3.12/site-packages/
$ patch -p0 < /tmp/vllm_qwen3_asr_strip_prefix.patch
```
