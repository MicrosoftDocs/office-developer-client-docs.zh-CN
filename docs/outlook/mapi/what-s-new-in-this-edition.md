---
title: 此版本中的新增功能
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a24cad75-1237-469f-b7f3-cbbb88f80d44
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 23a8b84af50cc8a046206ab37144d84c4c9b6d56
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329545"
---
# <a name="whats-new-in-this-edition"></a>此版本中的新增功能

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Microsoft Outlook 2013 MAPI 参考已更新为包括各种新功能的文档。 
  
## <a name="new-content"></a>新内容

已为以下功能添加了内容:
  
- [outlook 2013 MAPI 引用](getting-started-with-the-outlook-mapi-reference.md)入门主题已更新, 以参考有关您的 outlook 和 MAPI 功能的编程模型的详细信息, 以帮助您识别最适用于您的 api 和技术适合您的需求。 在以下主题中, 还对引用的技术文章的链接进行了修订: 
    
  - [Outlook MAPI 引用](outlook-mapi-reference.md)
    
  - [Outlook MAPI 引用概述](outlook-mapi-reference-overview.md)
    
- **邮件存储提供程序示例**-现已修改[包装的 PST 存储提供程序代码示例](message-store-provider-sample.md)以识别和适应 Outlook 2013。 有关详细信息, 请参阅本主题以前修订过的内容。 
    
- **自动完成流**-[昵称缓存](nickname-cache.md)主题 (以前为**Nk2 文件格式**) 已更新, 以反映 outlook 2013 和 outlook 2010 中的更改。 现已对以下主题进行了修订, 以提供有关 Microsoft Outlook 2003/microsoft Office Outlook 2007 和二进制文件分析的 nk2 文件格式开发人员指南的信息。 有关详细信息, 请参阅本主题以前修订过的内容。
    
  - [MAPI 配置文件](mapi-profiles.md)
    
  - [别名缓存](nickname-cache.md)
    
  - [自动完成流](autocomplete-stream.md)
    
- **interface**- [IAddrBook:: OpenEntry](iaddrbook-openentry.md)主题介绍了打开通讯簿条目并返回指向用于访问它的接口的指针的方法。 它以前在*ulFlags*参数**MAPI_GAL_ONLY**中包含了一个标志, 该参数可用于打开全局地址列表 (GAL), 并且已进行了修订, 以包含其定义。
    
- **属性**-已添加**PR_CONVERSATION_KEY**命名属性 ([PidTagConversationKey 规范属性](pidtagconversationkey-canonical-property.md)) 主题并与**IPM 相关。** 仅在 Outlook MAPI 中 MessageManager 邮件。 以下与 it 相关的主题和传输中性封装格式 (TNEF) 流文档已经过修订: 
    
  - [将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
    
  - [将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)
    
  - [将 TNEF 属性映射到 MAPI 属性](mapping-of-tnef-attributes-to-mapi-properties.md)
    
  - [attConversationID and attParentID](attconversationid-and-attparentid.md)
    
## <a name="previously-revised-content"></a>以前修改过的内容

在 Outlook MAPI 参考的早期版本中添加了内容, 了解以下功能:
  
- Microsoft Outlook 2013 允许非传统部署方案, 例如并行和即点即用。 这些方案可能会使用于加载正确的 MAPI 库的逻辑复杂化。 mapi 开发人员现在可以选择显式链接到 mapi 功能, 并且可以选择显式链接到默认 mapi 客户端 (例如, Msmapi32) 的 mapi 存根, 而无需通过 mapi 库和 Windows MAPI 存根。 有关与隐式链接相比的显式链接的详细信息, 请参阅[链接到 MAPI 函数](how-to-link-to-mapi-functions.md)。 在[CodePlex](https://mapistublibrary.codeplex.com/)网站上发布的**MAPI 存根库**提供了支持同时生成32位和64位 MAPI 应用程序的 Mapi32 的替代项。 
    
- 对**64 位 Microsoft Outlook 的支持**—更新适用 API 元素的参考主题, 以对应于支持64位 Outlook 的新头文件。 这些头文件可在[Outlook 2010: MAPI 头文件](https://www.microsoft.com/downloads/details.aspx?FamilyID=f8d01fc8-f7b5-4228-baa3-817488a66db1)中下载。 在中提供了一个新的代码示例, 以[查看 outlook 的版本](how-to-check-the-version-of-outlook.md), 以显示如何检查已安装的 outlook 版本是否为64位 Microsoft Outlook 2010 并已针对 outlook 2013 进行了修订。 如果您现有的32位 MAPI 应用程序将在安装了64位 Outlook 的64位操作系统上运行, 则需要将您的32应用程序重新生成为一个64位应用程序。 有关64位 Outlook 的 MAPI 支持的详细信息, 请参阅[在32位和64位平台上构建 mapi 应用程序](building-mapi-applications-on-32-bit-and-64-bit-platforms.md)。
    
- **邮件存储提供程序示例**-之前已更新[包装 PST 存储提供程序](message-store-provider-sample.md)以支持64位体系结构的示例。 此示例[初始化打包的 PST 存储区提供程序](initializing-a-wrapped-pst-store-provider.md)主题现已展开, 以提供有关 "打包的 pst 和 Unicode 路径" 的信息。 
    
- **自动完成流**-[昵称缓存](nickname-cache.md)主题 (以前为**Nk2 文件格式**) 已更新, 以反映 outlook 2013 和 outlook 2010 中的更改。 "自动完成" 列表 (在用户撰写电子邮件时显示在 "**收件人**"、 **"抄送**" 和 **"密件抄送**" 编辑框中) 的信息将被保存到本地计算机上的邮件的[自动完成流](autocomplete-stream.md)中, 如 "自动完成" 列表中显示的名称列表。而不是像在 Outlook 2007 中那样将其保存到文件中。 
    
  - 与自动完成流交互
    
  - 加载自动完成流
    
  - 保存自动完成流
    
- **对 mapi 客户端的快速关闭支持**— mapi 客户端现在可以启动快速关闭, 并让 mapi 子系统通知加载的提供程序, 以最大限度地减少快速关闭的数据丢失。 为客户端和提供程序添加了其他接口以支持快速关闭。 有关快速关机的详细信息, 请参阅[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)。
    
- **Outlook 项目的字段定义的流结构**—添加了[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性的二进制流的文档。 此属性指定 Outlook 项目的内置字段的所有自定义字段和数据绑定设置的定义。 
    
- **个人存储区重写**-添加了以下接口及其各自的方法, 以支持替代个人文件夹文件 (PST) 存储提供程序**pstdisablegrow 可**策略: 
    
    [IPSTOVERRIDEREQ:: IUnknown](ipstoverridereqiunknown.md)
    
    [IPSTOVERRIDE1:: IUnknown](ipstoverride1iunknown.md)
    
- **使用多个 Exchange 帐户**—添加了[MAPI 通讯簿 API](using-multiple-exchange-accounts.md)的文档。 此 API 已得到增强, 可在 microsoft outlook 2010 中支持多个 Exchange 帐户, 现在包括 microsoft outlook 2013。 若要使用多个 Exchange 帐户正确解析地址, 请使用采用帐户上下文的新函数, 以便对通讯簿的呼叫可以搜索正确的 Exchange 帐户。 
    
- **mapi 文件格式**— mapi 配置信息已扩展, 以说明如何在[mapisvc.inf 中注册服务和服务提供程序](registering-services-and-service-providers-in-mapisvc-inf.md)中使用路径。
    
- **属性**-除了文档之外, 还添加了以下带标签的属性, 以及以前添加的其他标记属性和命名属性:
    
  - [PidTagAddressBookChooseDirectoryAutomatically](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md)
    
  - [PidTagAssociatedSharingProvider](pidtagassociatedsharingprovider-canonical-property.md)
    
  - [PidTagRoamingBinary](pidtagroamingbinary-canonical-property.md)
    
  - [PidTagSenderSmtpAddress](pidtagsendersmtpaddress-canonical-property.md)
    
  - [PidTagSentRepresentingSmtpAddress](pidtagsentrepresentingsmtpaddress-canonical-property.md)
    
  - [PidTagStoreEntryIdEmsmdbV1](pidtagstoreentryidemsmdbv1-canonical-property.md)
    
- **MAPI 常量**—合并的[MAPI 常量](mapi-constants.md)已扩展。 在以前的版本中, 它们分布在许多主题中, 但现在在单个主题中收集, 使其更易于发现和使用。 此外, 还扩展了它们以提供更广泛的覆盖范围, 其中包括以下几节: 
    
  - Exchange 通讯簿和邮件存储错误代码的定义
    
  - Exchange Server 邮箱缓存模式配额的定义
    
## <a name="see-also"></a>另请参阅



[Outlook MAPI 引用入门](getting-started-with-the-outlook-mapi-reference.md)
  
[CodePlex](https://mapistublibrary.codeplex.com/)

