---
title: "MAM ポリシーを使用してアプリ データを保護する | Microsoft Intune"
description: "このトピックでは、モバイル アプリケーション管理ポリシーが、会社データの保護、データ損失の防止、および個人用情報と作業情報の個別管理に役立つしくみについて説明します。"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 66a5814ba34f9fd15460512b0a6d40566ec33401


---

# <a name="protect-app-data-using-mobile-application-management-policies-with-microsoft-intune"></a>Microsoft Intune でモバイル アプリケーション管理ポリシーを使用してアプリ データを保護する

## <a name="how-you-can-protect-app-data"></a>アプリ データを保護する方法
従業員は個人のタスクと仕事のタスクの両方にモバイル デバイスを使用しています。 従業員の生産性を維持したまま、意図的なデータ損失や意図しないデータ損失が起こらないようにする必要があります。  さらに、会社が管理していないデバイスを使用して従業員がアクセスする会社のデータを保護できるようにします。

Intune モバイル アプリケーション管理 (MAM) ポリシーを使用すれば、会社データを保護できます。 Intune MAM ポリシーは**どのモバイル デバイス管理 (MDM) ソリューションからも独立して**利用できるため、デバイスをデバイス管理ソリューションに登録するかどうかにかかわらず、MAM を使用して会社のデータを保護できます。 **アプリレベル ポリシー**を実装するだけで、会社のリソースへのアクセスを制限し、データを IT 部門の管理範囲内に保つことができます。

次のようなデバイスで実行されているアプリに対して、MAM ポリシーを構成することができます。

-   **Microsoft Intune に登録されているデバイス:** このカテゴリに属するデバイスは、通常、企業所有デバイスです。

-   **サードパーティの MDM ソリューションに登録されているデバイス:** このカテゴリに属するデバイスは、通常、企業所有デバイスです。

  > [!NOTE]
  > サードパーティのモバイル アプリケーション管理ソリューションやセキュア コンテナー ソリューションで MAM ポリシーを使用することは推奨されません。

-   **いずれの MDM ソリューションにも登録されていないデバイス:** このカテゴリに属するデバイスは、通常、Intune またはその他の MDM ソリューションで管理も登録もされていない社員所有のデバイスです。

> [!IMPORTANT]
> Office 365 サービスに接続する Office モバイル アプリ向けのモバイル アプリケーション管理ポリシーを作成することができます。 MAM ポリシーは、オンプレミス Exchange サービスや Skype for Business サービス、SharePoint サービスに接続するアプリではサポートされていません。

## <a name="benefits-of-using-mam-policies"></a>MAM ポリシーを使用するメリット

-   **アプリ レベルでの会社データの保護に役立ちます。** モバイル アプリケーション管理にはデバイス管理が必要ないため、管理対象のデバイスと管理対象ではないデバイスの両方で会社データを保護することができます。 管理の中心がユーザー ID になり、デバイスを管理する必要がなくなります。

-   **ユーザーの生産性に影響を与えることがなく、個人のコンテキストでアプリが使用される場合にはポリシーは適用されません。** ポリシーは仕事のコンテキストでのみ適用されるため、個人データに影響を与えることなく会社データを保護することが可能になります。

MDM を MAM ポリシーとともに使用することには付加的なメリットがあります。会社は MAM を MDM ありと MDM なしの両方で同時に使用できます。 たとえば、従業員は、会社が支給する電話に加えて個人のタブレットを使用する場合があります。 この場合、会社の電話は MDM に登録され、MAM ポリシーによって保護されていますが、個人のデバイスは MAM ポリシーで保護されるだけです。

- **MDM によりデバイスの保護を実現できます。** たとえば、デバイスへのアクセスに PIN を要求したり、デバイスに管理対象のアプリを展開したりすることができます。 また、MDM ソリューションを介してデバイスにアプリを展開することにより、アプリ管理をより制御できるようになります。

- **MAM ポリシーによりアプリ層の保護を実現できます。** たとえば、仕事のコンテキストでアプリを開くために PIN を要求したり、アプリ間でのデータの共有を禁止したり、会社のアプリ データを個人の記憶域に保存できないようにしたりするポリシーを作成できます。

## <a name="devices-that-support-mam"></a>MAM をサポートするデバイス
現在のところ、MAM ポリシーは次の OS でサポートされています。
-   iOS 8.1 以降
-   Android 4 以降

Windows デバイスは現在サポートされていません。
##  <a name="how-mam-policies-protect-app-data"></a>MAM ポリシーによるアプリ データ保護のしくみ

###  <a name="apps-without-mam-policies"></a>MAM ポリシーなしのアプリ

![MAM ポリシーが配置されていないときにデータがアプリ間を自由に移動するしくみを示す画像](../media/Apps_without_MAM_policies.png)

アプリを制限なしで使用すると、会社データと個人データが混在する可能性があります。 会社データが個人の記憶域に保存されたり、管理範囲外のアプリに転送されたりして、データが損失することがあります。 図の矢印はアプリ (会社と個人) と記憶域の間の制限されたデータ移動を示しています。

### <a name="data-protection-with-mam-policies"></a>MAM ポリシーでのデータ保護

![MAM ポリシーが適用されているときに会社のデータが保護されるしくみを示す画像](../media/Apps_with_mobile_app_policies.png)

MAM ポリシーを使用すれば、会社のデータをデバイスのローカル ストレージに保存する行為を防止し、MAM ポリシーで保護されていない他のアプリへのデータ移動を制限できます。 MAM ポリシー設定:
- **[名前を付けて保存] を禁止する**、**切り取り、コピー、貼り付けを制限する** のようなデータ再配置ポリシー。
- **アクセスの際にシンプルな PIN を要求する**、**脱獄されたデバイスまたは root 化されたデバイスで管理対象アプリが実行されることを禁止する**のようなアクセス ポリシー設定。

### <a name="data-protection-with-mam-policies-on-devices-that-are-managed-by-a-mdm-solution"></a>MDM ソリューションで管理されるデバイスの MAM ポリシーによるデータ保護

![Bring Your Own Devices (BYOD) デバイスで MAM ポリシーが機能するしくみを示す画像](../media/MAM_BYOD_November.png)

**MDM ソリューションに登録されているデバイスの場合**: 前の図は、MDM と MAM ポリシーによって提供される保護の各層を示しています。

MDM ソリューション:

-   デバイスを登録します。

-   アプリをデバイスに展開します。

-   継続的なデバイスのポリシー準拠と管理を提供します。

**MAM ポリシーが価値を高める理由:**

-   コンシューマー アプリやサービスに会社データがリークしないように支援します。

-   モバイル アプリに制限を適用します (名前を付けて保存、クリップボード、PIN など)。

-   デバイスからアプリを削除しないで、アプリから会社データをワイプします。


### <a name="data-protection-with-mam-policies-for-devices-without-enrollment"></a>登録のないデバイスに MAM ポリシーを適用するデータ保護

![管理対象デバイスで MAM ポリシーが機能するしくみを示す画像](../media/MAM_ManagedDevices_November.png)

上の図は、MDM がない場合にアプリ レベルでデータ保護ポリシーが機能するしくみを示しています。

MDM ソリューションに登録されていない BYOD デバイスの場合、MAM ポリシーによってアプリ レベルで会社データを保護することができます。

ただし、次のようないくつかの制約があることに注意してください。

-   アプリをデバイスに展開することはできません。 アプリはユーザーがストアから入手する必要があります。

-   これらのデバイスで証明書プロファイルをプロビジョニングすることはできません。

-   会社が Wi-Fi や VPN の設定をこれらのデバイスにセットアップすることはできません。


## <a name="multi-identity"></a>複数の ID

複数の ID をサポートするアプリの場合、アプリが作業コンテキストで利用されているときに MAM ポリシーが適用されてれば、仕事用や個人用など、複数のアカウントを利用して同じアプリにアクセスできます。  

たとえば、ユーザーが仕事用のアカウントを使用して OneDrive アプリを開始した場合、個人のストレージにファイルを移動できません。 ただし、ユーザーが個人のアカウントで OneDrive を使用する場合、個人の OneDrive から制限なしでデータをコピーしたり、移動したりできます。  

すべての Office モバイル アプリは複数 ID アクセスをサポートしています。

##  <a name="next-steps"></a>次のステップ
- [モバイル アプリケーション管理ポリシーを構成する準備](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [Microsoft Intune でのモバイル アプリケーション管理ポリシーの作成および展開](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->

