# english-learning-audio

[英文學習系統](https://github.com/wenchen123546/english-learning) 的所有音檔，以 GitHub Pages 提供給網站播放（網站本身在 Vercel，音檔放這裡就不佔 Vercel 的流量與部署空間）。

## `audio/`：單字與模擬考的預錄語音

- `audio/p<包號>-<雜湊>.mp3`＋`.json`：64 包，每包是很多段完整 MP3 接在一起，`.json` 是索引（片段編號 → [位置, 長度]）；網站用 Range 請求只抓需要的那一段
- 用 [Piper](https://github.com/rhasspy/piper)（MIT）產生，聲音 en_US-lessac-medium、en_GB-alan-medium
- 由主專案的 `tools/gen_audio.js` 產生，直接寫進這個資料夾（主專案和這個 repo 要放在同一層資料夾）；檔名含內容雜湊，內容變了檔名就會變

## `cap/`：會考聽力歷屆試題錄音

- `cap/<年>/<題號>.mp3`：國中教育會考英語聽力，每題一個檔（102 年只有一整段錄音：`cap/102/all.mp3`；109 年因疫情沒有考聽力）
- 來源：國中教育會考網站（心理與教育測驗研究發展中心）公布的歷屆聽力語音檔，轉成單聲道 40 kbps、去掉頭尾靜音
- 依《著作權法》第 9 條，依法令舉行之各類考試試題不得為著作權之標的

由主專案的 `tools/build_past_cap_listen.js` 產生。
