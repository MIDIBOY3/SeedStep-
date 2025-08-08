# Mini Sequencer — Dual Track (Browser)

シンプルな**2トラック**・**16ステップ**のブラウザシーケンサー兼ミニシンセ。  
**Chance / Range / Tie / Slide / Accent / Velocity / Swing / Filter / Delay / Reverb / MIDI書き出し / Permalink / Xシェア**をサポート。

## 使い方
- `index.html` をブラウザで開き、任意の場所を一度クリック → **Start**。
- **One‑Note**…両トラックを「全ON＋Chance=100%＋Range=0」に初期化（1音ベタ打ちから育てる）。
- **Global Chance**…各ステップのStep Chanceと乗算して最終確率を決定。水色のぼかしが「鳴る予定」。

### トラック（A/B）
- **Length**…パターン長（1–16）。
- **Key / Scale / Oct / Range**…音階と発展幅。**Rand Now**で16ステップの度数をランダム。**Auto Rand / 16**で1サイクルごとに再抽選。
- **Filter**…各トラック独立の**Cutoff / Resonance**。

### ステップ編集（Step Editor）
- グリッドを**クリック**でON/OFF ＋ 選択。**Ctrl/Cmd+クリック**で選択のみ。
- Editorで以下を編集：
  - **On/Off / Velocity / Step Chance / Accent / Tie / Slide**
  - **Accent Velocity**（アクセント時のベロシティ）
  - **Editor Target**（編集対象ステップを番号で移動）
  - **Rnd Step Chance / Rnd Accents**（16ステップ分一括ランダム）

### 再生系
- **Tempo / Swing / Gate**…グローバル。Swingは16分スウィング。
- **Delay / Reverb**…デフォルトOFF。**ミックスを上げた時だけ**ノードを生成（Chrome/macOS対策）。

### MIDI書き出し
- **Export MIDI (2 tracks)**…**Type-1**（テンポメタ＋2ノートトラック）。1小節。Chance適用後の実際のノートのみを書き出し。

## GitHub Pages で公開する
1. GitHubで新規リポジトリ作成（例: `mini-sequencer`）。
2. `Add file > Upload files` で `index.html` と `README.md` をアップロード。
3. リポジトリの **Settings > Pages** へ移動。
4. **Source** を `Deploy from a branch` に、**Branch** を `main` / **Folder** を `/root` に設定し **Save**。
5. 数分後、`https://<ユーザー名>.github.io/mini-sequencer/` で公開完了。  
   このURLをXに貼れば、誰でもブラウザで即再生。

## 互換メモ
- Chrome/macOS の初回無音対策として、**ユーザー操作でAudioContextをresume**、かつ**ドライ信号は常時直結**。FXは**遅延生成**で安全に動作します。

---

© 2025 Shinya — Built for quick musical sketching.
