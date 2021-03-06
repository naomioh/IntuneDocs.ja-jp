---
title: Android for Work のコンプライアンス設定
description: このトピックでは、Android for Work と互換性のある Android デバイスのデバイス コンプライアンス ポリシーの設定について説明します。
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 02/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 085cca57365da0df9dd739c3a1b2b0c6dd6fded6
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a>Microsoft Intune での Android for Work デバイス向けのコンプライアンス ポリシー設定

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

このトピックで説明するポリシー設定は、Android for Work デバイスに適用されます。

その他のプラットフォームに関する情報を探している場合は、次のいずれかを選択します。
> [!div class="op_single_selector"]
> - [Android 向けのコンプライアンス ポリシー設定](android-compliance-policy-settings-in-microsoft-intune.md)
> - [iOS デバイス向けのコンプライアンス ポリシー設定](ios-compliance-policy-settings-in-microsoft-intune.md)
> - [Windows デバイス向けのコンプライアンス ポリシー設定](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>システム セキュリティ設定
### <a name="password"></a>パスワード
- **モバイル デバイスのロック解除にパスワードを必要とする:** デバイスにアクセスするユーザーにパスワードを入力するよう求める場合は、**[はい]** に設定します。

-  **パスワードの最小文字数:** ユーザーのパスワードに含まれている必要がある数字または文字の最小数を指定します。

- **パスワードの品質:** 指定したパスワード要件が、デバイスに構成されているかどうかをこの設定で検出します。 この設定を有効にすると、Android デバイスで特定のパスワード要件を構成することが必須になります。 次の中から選択します。
  -   **低レベルのバイオメトリック セキュリティ**
  - **必須**
  -   **最小数の数字**
  -   **最小数の英字**
  -   **最小数の英数字**
  -   **英数字と記号**

- **デバイスの画面がロックされるまでの非アクティブな時間 (分):** ユーザーがパスワードを再入力しなければならなくなるまでのアイドル時間を指定します。

- **パスワードの有効期限 (日数):** 新しいパスワードの作成が必要となるまでのユーザーのパスワードの有効日数を選択します。

- **パスワードの履歴を記憶する:** この設定を **[前のパスワードの再利用を防止]** と組み合わせて使用することで、以前使用されていたパスワードをユーザーが作成することを制限します。

- **前のパスワードの再利用を防止:** **[パスワードの履歴を保存する]** が選択されている場合は、再利用できない、以前に使用されていたパスワードの数を指定します。

- **デバイスがアイドル状態から戻るときにパスワードを必須とする:** この設定は、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定と組み合わせて使用する必要があります。 エンドユーザーは、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定で指定された時間非アクティブの状態が続いたデバイスにアクセスしようとすると、パスワードを入力するように求められます。

### <a name="encryption"></a>暗号化
- **モバイル デバイスで暗号化を必要とする:** Android for Work デバイスは暗号化が適用されるので、この設定を構成する必要はありません。

## <a name="device-health-and-security-settings"></a>デバイスの正常性とセキュリティ設定

- **デバイスの脱獄または root 化を認めない:** この設定を有効にした場合、脱獄デバイスは非準拠として評価されます。
- **デバイスで提供元不明のアプリのインストールを禁止することを必須にする:** Android for Work デバイスでは、不明なソースからのインストールが常に制限されるので、この設定を構成する必要はありません。 。  

- **USB デバッグの無効化を必須にする**: Android for Work デバイスでは、USB デバッグは無効にされているので、この設定を構成する必要はありません。

- **最低限の Android セキュリティ パッチ レベル**: この設定を使用して、Android の修正プログラムの最小レベルを指定します。  修正プログラムがこのレベルに達していないデバイスは非対応になります。 日付は YYYY-MM-DD の形式で指定する必要があります。
- **デバイス脅威保護を有効にすることを必須とする**: この設定は、デバイス脅威保護ソリューションからのリスク評価をコンプライアンスの条件とする場合に使用します。 最大許容脅威レベルとして次のいずれかを選択します。

  - **[なし (セキュリティ保護)]**: これはセキュリティ上最も安全です。 デバイスにはいかなる脅威も存在できないことを意味します。 デバイスで何らかのレベルの脅威が検出された場合、非準拠と評価されます。
  - **[低]**: 存在する脅威が低レベルの場合のみ、デバイスは準拠として評価されます。 低レベルより高い脅威が存在する場合、デバイスは非準拠状態になります。
  - **[中]**: デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠として評価されます。 デバイスで高レベルの脅威が検出された場合は、非準拠と判定されます。
  - **[高]**: 最も安全性の低い状態です。 基本的にすべての脅威レベルが許容されるため、通常、このソリューションはレポートを目的とした場合にのみ役に立ちます。

  詳細については、「[Intune での Lookout デバイス コンプライアンス ポリシーの作成](create-lookout-device-compliance-policy.md)」を参照してください。

## <a name="device-property-settings"></a>デバイスのプロパティの設定
- **必要な最小 OS バージョン**: デバイスが最小オペレーティング システム (OS) バージョンの要件を満たしていない場合、非準拠として報告されます。
  アップグレード方法に関する情報のリンクが表示されます。 エンド ユーザーは、デバイスのアップグレードを行うことを選択できます。アップグレード後は、会社のリソースにアクセスできます。

- **許可される最大 OS バージョン**: ルールに指定されたものより新しいバージョンのオペレーティング システム (OS) がデバイスで使用されている場合、会社のリソースへのアクセスがブロックされ、IT 管理者に問い合わせることをユーザーに促すメッセージが表示されます。対象のオペレーティング システム バージョンを許可するようにルールが変更されるまで、このデバイスを使用して会社のリソースへのアクセスすることはできません。
