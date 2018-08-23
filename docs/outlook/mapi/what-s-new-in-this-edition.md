---
title: 此版本的新增功能
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a24cad75-1237-469f-b7f3-cbbb88f80d44
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: 7325c42fe7e9c1e043609d5503a3782522f76188
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590055"
---
# <a name="whats-new-in-this-edition"></a>此版本的新增功能

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
Microsoft Outlook 2013 MAPI 参考已更新以包括有关各种新功能的文档。 
  
## <a name="new-content"></a>新内容

内容已添加对以下功能：
  
- [Getting Started with Outlook 2013 MAPI 参考](getting-started-with-the-outlook-mapi-reference.md)主题已更新，以引用编程模型可帮助您确定 Api 和技术的大多数您 Outlook 和 MAPI 的功能的全面了解适用于您的需求。 指向引用的技术文章还具有以下主题已修订时间： 
    
  - [Outlook MAPI 引用](outlook-mapi-reference.md)
    
  - [Outlook MAPI 引用概述](outlook-mapi-reference-overview.md)
    
- **消息存储提供程序示例**—[示例自动换行 PST 的存储提供程序](message-store-provider-sample.md)现在已修改代码以识别和容纳 Outlook 2013。 详细信息，请参阅本主题中的以前进行了修订内容。 
    
- **记忆式键入流**—[昵称缓存](nickname-cache.md)主题，以前**Nk2 文件格式**，具有已更新以反映为 Outlook 2010 或 Outlook 2013 中的更改。 以下主题现在已修订以提供有关.nk2 文件格式的开发人员指南的 Microsoft Outlook 2003/Microsoft Office Outlook 2007 和分析的二进制文件的信息。 详细信息，请参阅本主题中的以前进行了修订内容。
    
  - [MAPI 配置文件](mapi-profiles.md)
    
  - [别名缓存](nickname-cache.md)
    
  - [自动完成流](autocomplete-stream.md)
    
- **接口**- [IAddrBook::OpenEntry](iaddrbook-openentry.md)主题的文档打开的通讯簿条目，并返回到用于访问该接口的指针的方法。 以前，它包含*ulFlags*参数， **MAPI_GAL_ONLY**，它可用于打开全局地址列表 (GAL)，仅，并已经过修改，包括其定义中的标志。
    
- **属性**— **PR_CONVERSATION_KEY**名为属性 （[PidTagConversationKey 规范属性](pidtagconversationkey-canonical-property.md)） 主题已添加，并将与**IPM 关联。MessageManager**仅在 Outlook 的 MAPI 邮件。 修改其和传输中性封装格式 (TNEF) 流文档与相关的以下主题： 
    
  - [将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
    
  - [将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)
    
  - [将 TNEF 属性映射到 MAPI 属性](mapping-of-tnef-attributes-to-mapi-properties.md)
    
  - [attConversationID and attParentID](attconversationid-and-attparentid.md)
    
## <a name="previously-revised-content"></a>以前修订后的内容

在以前版本的 Outlook MAPI 参考 （英文） 的以下功能中添加了内容：
  
- Microsoft Outlook 2013 允许-并行等单击即点即用的非传统的部署方案。 这些方案，则会增加复杂性用于加载的正确的 MAPI 库的逻辑。 MAPI 开发人员现在可以选择将显式链接到 MAPI 函数，并可以选择显式链接到默认 MAPI 客户端 (例如，Msmapi32.dll 的 Outlook) 的 MAPI 存根而无需经过 MAPI 库和 Windows MAPI 存根。 有关用于隐式链接显式链接的详细信息，请参阅[MAPI 函数的链接](how-to-link-to-mapi-functions.md)。 **MAPI 存根库**，在[CodePlex](http://mapistublibrary.codeplex.com/)网站发布提供支持构建 32 位和 64 位的 MAPI 应用程序的 Mapi32.lib 顺便替换。 
    
- **64 位 Microsoft Outlook 支持**— 适用 API 元素参考主题已进行了更新以对应于支持 64 位 Outlook 的新头文件。 将在下载这些头文件[Outlook 2010: MAPI 头文件](http://www.microsoft.com/downloads/details.aspx?FamilyID=f8d01fc8-f7b5-4228-baa3-817488a66db1)。 在[检查版本的 Outlook](how-to-check-the-version-of-outlook.md)以显示如何检查安装的 Outlook 版本是否是 64 位 Microsoft Outlook 2010 和 Outlook 2013 已修订提供的新代码示例。 如果您现有的 32 位 MAPI 应用程序将运行 64 位操作系统上安装的 64 位 Outlook，您需要重新生成 32 位应用程序作为 64 位应用程序。 有关 64 位 Outlook 的 MAPI 支持的详细信息，请参阅[32 位和 64 位平台上构建 MAPI 应用程序](building-mapi-applications-on-32-bit-and-64-bit-platforms.md)。
    
- **消息存储提供程序示例**—[示例自动换行 PST 的存储提供程序](message-store-provider-sample.md)具有先前已进行了更新以支持 64 位体系结构。 现在已扩展的示例[初始化自动换行 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)的主题提供信息的"Wrapped PST 和 Unicode 路径。" 
    
- **记忆式键入流**—[昵称缓存](nickname-cache.md)主题，以前**Nk2 文件格式**，已更新，以反映为 Outlook 2010 或 Outlook 2013 中的更改。 信息记忆式键入列表中，为用户撰写电子邮件时，**到**、**抄送**和**密件抄送**编辑框中显示的名称列表，如现在保存到一条消息[记忆式键入流](autocomplete-stream.md)本地计算机上而不是将其保存到一个文件，如 Outlook 2007 中所示。 
    
  - 与记忆式键入流交互
    
  - 加载记忆式键入流
    
  - 保存记忆式键入流
    
- **MAPI 客户端的快速关闭支持**— MAPI 客户端可以立即启动的快速关闭并具有通知加载提供程序地减少数据丢失从快速关闭 MAPI 子系统。 为客户端和提供程序，以支持快速关闭，添加了其他接口。 有关快速关闭的详细信息，请参阅[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)。
    
- **为某个 Outlook 项目的字段定义的流结构**— 文档的二进制流[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性已添加。 此属性指定的所有自定义字段和数据绑定的内置字段的 Outlook 项目的设置的定义。 
    
- **重写个人存储**— 以下接口和其各自方法添加以支持替代个人文件夹文件 (PST) 存储提供程序**PSTDisableGrow**策略： 
    
    [IPSTOVERRIDEREQ::IUnknown](ipstoverridereqiunknown.md)
    
    [IPSTOVERRIDE1::IUnknown](ipstoverride1iunknown.md)
    
- **使用多个 Exchange 帐户**— 已添加的[MAPI 地址簿 API](using-multiple-exchange-accounts.md)文档。 此 API 已增强后，可在 Microsoft Outlook 2010 中支持多个 Exchange 帐户，现在包括 Microsoft Outlook 2013。 若要解决正确使用多个 Exchange 帐户的地址，请使用拍摄帐户上下文，以便调用通讯簿搜索正确的 Exchange 帐户的新功能。 
    
- **MAPI 文件格式**— 介绍如何使用路径中[注册服务和服务提供商 MapiSvc.inf](registering-services-and-service-providers-in-mapisvc-inf.md)进行了扩展 MAPI 配置信息。
    
- **属性**— 以下标记的属性已添加除了文档之外的其他 38 标记属性和名为之前已添加的属性：
    
  - [PidTagAddressBookChooseDirectoryAutomatically](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md)
    
  - [PidTagAssociatedSharingProvider](pidtagassociatedsharingprovider-canonical-property.md)
    
  - [PidTagRoamingBinary](pidtagroamingbinary-canonical-property.md)
    
  - [PidTagSenderSmtpAddress](pidtagsendersmtpaddress-canonical-property.md)
    
  - [PidTagSentRepresentingSmtpAddress](pidtagsentrepresentingsmtpaddress-canonical-property.md)
    
  - [PidTagStoreEntryIdEmsmdbV1](pidtagstoreentryidemsmdbv1-canonical-property.md)
    
- **MAPI 常量**— 已扩展合并的[MAPI 常量](mapi-constants.md)。 在以前版本中它们分布在多个主题，但现在收集使其更容易发现和使用单个主题中。 他们还已扩展以提供更复杂的范围包括以下各节： 
    
  - Exchange 通讯簿和消息存储错误代码的定义
    
  - Exchange Server 邮箱定义缓存模式配额
    
## <a name="see-also"></a>另请参阅



[Outlook MAPI 引用入门](getting-started-with-the-outlook-mapi-reference.md)
  
[CodePlex](http://mapistublibrary.codeplex.com/)

