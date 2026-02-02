# misc

(1) vllm_qwen3_asr_strip_prefix.patch
Qwen3-ASRの qwen-asr-serve（OpenAI互換APIサーバ）の出力から言語プリフィックス（"language Japanese<asr_text>"のような記述）を除去するためのパッチ
$ cd ${HOME}/miniconda3/envs/qwen3-asr/lib/python3.12/site-packages/
$ patch -p0 < vllm_qwen3_asr_strip_prefix.patch
