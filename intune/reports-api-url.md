---
title: Intune データ ウェアハウス API エンドポイント
titlesuffix: Microsoft Intune
description: リファレンス トピックでは Intune データ ウェアハウス API URL 構造について説明します。
keywords: Intune データ ウェアハウス
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b25140cb5c3c8c70ff42186352362c57dcf6ee7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune データ ウェアハウス API エンドポイント

特定のロールベースのアクセス制御と Azure Active Directory 資格情報を使用するアカウントに、Intune データ ウェアハウス API を使用できます。 次に、OAuth 2.0 を使用して Azure AD に対して REST クライアントを承認します。 最後に、データ ウェアハウス リソースを呼び出すことができる有効な URL を形成します。

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>承認

Azure Active Directory (Azure AD) では、OAuth 2.0 を使用して Azure AD テナントの Web アプリケーションと Web API へのアクセスを承認できます。 このガイドは言語に依存していません。いずれのオープンソース ライブラリも使用せずに、HTTP メッセージを送受信する方法について説明します。 OAuth 2.0 承認コード フローについては、OAuth 2.0 仕様の[セクション 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) を参照してください。

詳細については、「[OAuth 2.0 と Azure Active Directory を使用した Web アプリケーションへのアクセスの承認](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)」を参照してください。

## <a name="api-url-structure"></a>API URL 構造

データ ウェアハウス API エンドポイントは、各セットのエンティティを読み取ります。 API は、**GET** HTTP 動詞と、クエリ オプションのサブセットをサポートしています。

Intune の URL は、次の書式を使用しています。  
https://fef.{<strong><em>location</em></strong>}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{<strong><em>entity-collection</em></strong>}?api-version={<strong><em>api-version</em></strong>}

URL には、次の要素が含まれています。

| 要素 | 例 | 説明 |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Azure Portal でデータ ウェアハウス API ブレードを表示すると、ベース URL を確認できます。 |
| entity-collection | dates | OData エンティティ コレクションの名前。 データ モデルのコレクションとエンティティの詳細については、「[Data Model](reports-ref-data-model.md)」(データ モデル) を参照してください。 |
| api-version | beta | Version はアクセスする API のバージョンです。 詳細については、「[API のバージョン情報](#API-version-information)」を参照してください。 |


## <a name="api-version-information"></a>API のバージョン情報

API の現在のバージョンは `beta` です。 

## <a name="odata-query-options"></a>OData クエリのオプション

現在のバージョンは、OData クエリ パラメーター `$filter, $orderby, $select, $skip,` と `$top` をサポートしています。