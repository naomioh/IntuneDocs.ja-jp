---
title: "Windows ストア アプリを Intune に追加する方法 | Intune Azure プレビュー | Microsoft Docs"
description: "Intune Azure プレビュー: Windows ストア アプリを Intune に追加する方法について説明します。"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 80fe042dbdc909d1c81098567b1a87d8b089cc19
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Windows ストア アプリを Microsoft Intune に追加する方法

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Azure ポータルにサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[アプリの管理]** を選択します。
4. **[モバイル アプリ]** ワークロードで、**[管理]** > **[アプリ]** の順に選択します。
5. アプリの一覧の上にある **[追加]** を選択します。
6. **[アプリの追加]** ブレードで、**[アプリ情報]** を選択します。
7. **[アプリの編集]** ブレードで、以下の情報を構成します。 構成が終わったら、**[追加]** をクリックします。 選択したアプリによっては、このブレード内の一部の値が自動的に入力されている場合があります。
    - **[アプリ名]** - アプリの名前を入力します。この名前は会社のポータルに表示されます。 使用するアプリ名はすべて一意にします。 同じアプリ名が&2; つ存在する場合、会社のポータルではそのいずれかのみがユーザーに表示されます。
    - **[アプリの説明]** - アプリの説明を入力します。 これは会社のポータルでユーザーに表示されます。
    - **発行元** - アプリの発行元の名前を入力します。
    - **[アプリ ストア URL]** - 作成するアプリのアプリ ストア URL を入力します。
    - **[オペレーティング システムの最小要件]** - アプリをインストールできる最小限のオペレーティング システム バージョンを一覧から選択します。 これよりも前のオペレーティング システムがアプリの割り当て先デバイスにインストールされている場合、そのアプリはインストールされません。
    - **[カテゴリ]** (省略可能) -&1; つ以上の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。 会社のポータルを閲覧するとき、ユーザーにとってアプリを探すのが簡単になります。
    - **[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探す際に、会社のポータルのメイン ページでアプリを目立つように表示します。
    - **[情報 URL]** - 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。 この URL は会社のポータルでユーザーに表示されます。
    - **[プライバシー URL]** - 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。 この URL は会社のポータルでユーザーに表示されます。
    - **[開発者]** - 必要に応じて、アプリ開発者の名前を入力します。
    - **[所有者]** - 必要に応じて、このアプリの所有者の名前 ("**人事部**" など) を入力します。
    - **[メモ]** - このアプリに関連付けるメモを入力します。
    - **[アップロード アイコン]** - アプリに関連付けるアイコンをアップロードします。 ユーザーが会社のポータルを参照するとき、アプリにこのアイコンが表示されます。
8. 構成が終了したら、**[アプリの追加]** ブレードで、**[保存]** を選択します。

作成したアプリはアプリの一覧に表示され、選択したグループに割り当てることができるようになります。 詳細については、[アプリをグループに割り当てる方法](/intune-azure/manage-apps/deploy-apps)に関するページを参照してください。