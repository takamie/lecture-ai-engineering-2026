# 第3回 解答

## 演習

- 第1回（素のLLM）とエージェントの回答の違い：ツールの説明文を読んでやり方を決めている
- `--trace` で見えたツール呼び出し（ツール名と引数）：LLMを２回よんでいる
- 1つの質問での LLM 呼び出し回数（`requests`）：２回
- 追加したツールと、docstring に書いた説明：
    講座の用語集から用語を検索し、定義と、どの回で扱うかを返す。
    答える前に使うこと。query には調べたい用語を1つだけ入れる（例: "LoRA"）。

## 宿題

- 取り組んだレベル：基礎
- やったこと：
agent.pyのINSTRUCTIONSに以下の文を追加
"""
　- 学習の参考文献を答える。
"""
同じ問を実行し比較
　uv run python -m app.agent --trace "LoRAとQLoRAの違いは？"

- 結果：
■はじめの回答
* **LoRA**: 事前学習済みの重みは固定したまま、重みの更新分を2つの小さな低ランク行列（低ランク行列）で表し、その部分だけを学習するPEFT（Parameter-Efficient Fine-Tuning）手法です。学習パラメータやメモリを大幅に削減できます。
* **QLoRA**: ベースモデルの重みを4ビットなどに量子化（Quantization）してさらにメモリを節約したうえで、LoRAによるファインチューニングを行う手法です。これにより、より大きなモデルを小さなGPU環境でも扱えるようになります。

関係する回：第2回

■問を追加しての回答
* **LoRA**
  事前学習済みの重みは固定したまま、重みの更新分を2つの小さな行列の積（低ランク行列）で表し、その小さな行列だけを学習するPEFT手法です。学習するパラメータが少なく、学習結果（アダプタ）も小さいファイルで保存できます。
* **QLoRA**
  ベースモデルの重みを4ビットなどに量子化してメモリを節約したうえで、LoRAで学習する手法です。これにより、より大きなモデルを小さなGPUで扱えるようになります。

参考文献：
- [Hugging Face PEFT Documentation](https://huggingface.co/docs/peft/index)
- LoRA論文: *LoRA: Low-Rank Adaptation of Large Language Models*
- QLoRA論文: *QLoRA: Efficient Finetuning of Quantized LLMs*

（第2回）

- 気づき・疑問：INSTRUCTIONSをちゃんと見て回答してくれているのがわかった。関連論文などネット上など検索してくれているのがわかった。
