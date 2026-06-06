# fitra-aaa

Raytac **AN54LQ-15**（Nordic **nRF54L15** 搭載 BLE モジュール）を中心とした、
**SlimeVR フルボディトラッカー基板**（[Smol Slime](https://docs.slimevr.dev/smol-slimes/index.html) 向け）の
KiCad 設計プロジェクトです。

## 概要

| 機能 | 部品 |
|------|------|
| MCU / BLE SoC | Raytac **AN54LQ-15**（Nordic **nRF54L15** 搭載モジュール） |
| 6軸 IMU センサ | STMicroelectronics **LSM6DSV** |
| 電源管理（PMIC） | Nordic Semiconductor **NPM2100** (QFN) |
| バッテリ接続 | JST **SM03B** コネクタ |

## Smol Slime / SlimeVR について

本基板は、nRF 系 SoC 向けの SlimeVR トラッカー firmware「**Smol Slime**」で動作する
トラッカーハードウェアです。

- Smol Slime ドキュメント: <https://docs.slimevr.dev/smol-slimes/index.html>
- トラッカー firmware（SlimeNRF）: <https://github.com/SlimeVR/SlimeVR-Tracker-nRF>
- SlimeVR プロジェクト: <https://docs.slimevr.dev/>

## 必要環境

- **KiCad 9 以降**（回路図は KiCad 10 で保存されています。**KiCad 10 を推奨**）

## 開き方

`fitra-aaa.kicad_pro` を KiCad で開いてください。

## 外部ライブラリについて

回路図・基板で使用しているシンボル/フットプリントは設計ファイル（`*.kicad_sch` の
`lib_symbols` および `*.kicad_pcb`）に**埋め込まれている**ため、リポジトリをクローン
すればそのまま**閲覧・製造データ（ガーバー等）の生成が可能**です。外部ライブラリを
再ダウンロードしなくても基板は完全に表示されます。

部品のシンボル/フットプリントを**再編集**する場合のみ、元ライブラリが必要です。

### 同梱しているライブラリ

| ライブラリ | 内容 | ライセンス |
|-----------|------|-----------|
| `libraries/local_lib*` | 自作シンボル/フットプリント（SWD パッド, VBAT スルー, nPM2100-QFN 等） | 本プロジェクトに準ずる（CC-BY-4.0） |

### 同梱していないライブラリ（設計に埋め込み済み／再編集時に各サイトから取得）

下記の部品ライブラリは**単体ファイルとしてはリポジトリに含めていません**。各提供元の
ライセンス・利用規約により、ライブラリ単体での再配布が制限されているためです。
シンボル/フットプリントは設計ファイルに埋め込み済みなので閲覧・製造には支障ありません。

| 部品 | 取得元 | 備考 |
|------|--------|------|
| NPM2100（PMIC） | [SnapEDA](https://www.snapeda.com/) | CC-BY-SA 4.0。単体ライブラリの再配布は制限あり。設計の一部としての利用は許諾 |
| LSM6DSV16XTR（IMU） | [SnapEDA](https://www.snapeda.com/) | 同上 |
| SM03B-SRSS-TB（コネクタ） | [SnapEDA](https://www.snapeda.com/) | 同上 |
| AN54LQ（BLE モジュール） | [Raytac](https://www.raytac.com/) | Altium 形式。提供元規約により同梱不可 |

> 再編集が必要な場合は各提供元から入手し、`libraries/` 配下に配置のうえ
> `fp-lib-table` / `sym-lib-table` に再登録してください。

## クレジット / 帰属表示

- **NPM2100** / **LSM6DSV16XTR** / **SM03B-SRSS-TB** のシンボル・フットプリント・3D モデルは
  [SnapEDA](https://www.snapeda.com/)（CC-BY-SA 4.0）提供のものを設計に組み込んで使用しています。

## ライセンス

本リポジトリの設計データ（回路図・基板・自作ライブラリ）は
**Creative Commons Attribution 4.0 International (CC-BY-4.0)** で公開します。

同梱・参照する各部品ライブラリは、それぞれの提供元（SnapEDA, Raytac 等）
のライセンス・利用規約に従います。
