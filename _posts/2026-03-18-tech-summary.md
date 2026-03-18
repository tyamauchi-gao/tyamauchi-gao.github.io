---
layout: post
title: "Tech Summary - 2026/03/18"
date: 2026-03-18
categories: [tech-summary]
sources:
  - url: "https://x.com/GoogleCloudTech/status/2033953579824758855?s=20"
    title: "ADK開発者が知っておくべき5つのエージェントスキル設計パターン"
  - url: "https://x.com/code/status/2033981896690946488?s=20"
    title: "Use Agent Skills in VS Code"
  - url: "https://x.com/trq212/status/2033949937936085378"
    title: "Lessons from Building Claude Code: How We Use Skills"
  - url: "https://zenn.dev/komlock_lab/articles/280ff7f1ba9b13"
    title: "NemoClaw触ってみた：OpenClawのセキュリティ問題を解消できるのか？"
  - url: "https://dev.classmethod.jp/articles/google-cloud-recommended-security-checklist/"
    title: "Google Cloud が推奨セキュリティチェックリストを公開"
---

今日のテック記事まとめです。

---

## 1. [ADK開発者が知っておくべき5つのエージェントスキル設計パターン](https://x.com/GoogleCloudTech/status/2033953579824758855?s=20)

Google CloudがAgent Development Kit（ADK）開発者向けに、エージェントスキルの設計パターンを5つ紹介。エージェントAIの構築において、再利用可能で堅牢なスキル設計が重要であることを示し、具体的なパターンを通じて実装のベストプラクティスを提案している。

**キーポイント:**
- ADK（Agent Development Kit）を使ったエージェント開発における設計パターンの体系化
- 再利用可能なスキル設計によるエージェントの機能拡張アプローチ
- Google Cloudのエージェントエコシステムにおけるベストプラクティスの提示

---

## 2. [Use Agent Skills in VS Code](https://x.com/code/status/2033981896690946488?s=20)

VS Codeがエージェントスキル機能を導入。指示やリソースをパッケージ化し、エージェントが再利用可能な機能として活用できるようになった。これにより、開発者は特定のタスクやワークフローを定義済みのスキルとしてまとめ、AIエージェントの能力を効率的に拡張できる。

**キーポイント:**
- エージェントスキルにより、指示・スクリプト・リソースを1つのパッケージとして管理可能
- VS Code内のAIエージェントが再利用可能な機能モジュールとしてスキルを利用
- 開発ワークフローの自動化と標準化が促進される

---

## 3. [Lessons from Building Claude Code: How We Use Skills](https://x.com/trq212/status/2033949937936085378)

Anthropicの開発チームがClaude Codeのスキル機能について、開発過程での教訓を共有。スキルは指示・スクリプト・リソースを含むフォルダとして構成され、Claude アプリ、Claude Code、API全体で利用可能。必要な情報のみを段階的にロードする「Progressive Disclosure」の設計思想により、効率性とパフォーマンスを両立している。

**キーポイント:**
- スキルは構成性（Composable）・移植性（Portable）・効率性（Efficient）の3つの特性を持つ
- Progressive Disclosure: メタデータ→SKILL.md本文→バンドルリソースの3段階で必要な情報のみロード
- 実行可能コードをスキルに含めることで、トークン生成より信頼性の高い処理が可能

---

## 4. [NemoClaw触ってみた：OpenClawのセキュリティ問題を解消できるのか？](https://zenn.dev/komlock_lab/articles/280ff7f1ba9b13)

NVIDIAが発表したNemoClawは、OpenClawエージェントをセキュリティ・プライバシー層で保護するオープンソーススタック。Landlock LSMなどのカーネル層技術を活用し、ファイルシステムやネットワークを宣言的ポリシーで制御する。著者がAlpha版を実装検証し、機密データを扱う企業利用では「事実上必須」となる可能性を指摘している。

**キーポイント:**
- NemoClawは「全閉→必要な穴だけ開ける」設計で、サンドボックス内でOpenClawを隔離実行
- アプリケーション×ホストの組み合わせでネットワーク制御を行い、curl等の任意通信を物理的に遮断
- YAML形式の宣言的ポリシーにより、GitOpsベースでの運用管理が可能

---

## 5. [Google Cloud が推奨セキュリティチェックリストを公開](https://dev.classmethod.jp/articles/google-cloud-recommended-security-checklist/)

Google Cloudが「Google Cloud minimum viable secure platform（GCMVSP）」というセキュリティチェックリストを公開。60個のセキュリティコントロールが3段階（ベーシック・中級・上級）に分類され、組織の成熟度に応じて段階的に実装できる。Terraformによるサンプルコードも提供されており、実装スピードを大幅に向上させることが可能。

**キーポイント:**
- 3段階の実装レベル: ベーシック（全組織向け）、中級（基礎を超えた組織向け）、上級（高度な制御が必要な組織向け）
- 6つのセキュリティドメイン: 認証と認可、組織、インフラストラクチャ、データ保護、ネットワークセキュリティ、モニタリング・ロギング・アラートをカバー
- IaC対応: TerraformサンプルコードがGitHubで公開されており、即座にデプロイ可能

---

*この記事はClaude Codeによって自動生成されました。*
