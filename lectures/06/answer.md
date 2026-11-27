# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：[search_materials]
- STEP 2 の [tool call]：glossary_search_glossary({'query': '3レベル'})
- STEP 3 の [tool call]：fetch_fetch({'url': 'https://modelcontextprotocol.io/'})
- STEP 4 の [tool call]：aws_aws___search_documentation({'search_phrase': 'Amazon S3 バージョニング 概要', 'topics': ['general']})
- 気づき・疑問：外部サーバーを共用できれば、自分ですべて用意しなくても組み合わせだけで様々な世界観が作れる可能性を感じた。

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎
- やったこと：mcp.server.pyに以下の行を追加
　　　　server.tool()(tools.get_lecture_summary)
- 結果：tool表時に対して、
[glossary_get_lecture_summary]
  指定した回（1始まりの整数）の講義の要点を返す
  と返してきたので、ツール追加できたことを確認した。
- 気づき・疑問：ツール追加して使えることは面白いと思った
