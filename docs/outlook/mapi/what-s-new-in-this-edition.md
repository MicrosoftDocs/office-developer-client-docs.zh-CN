---
title: 此版本的新增功能
manager: soliver
ms.date: 2/09/2020
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a24cad75-1237-469f-b7f3-cbbb88f80d44
description: 上次修改时间：2020 年 2 月 9 日
ms.openlocfilehash: 3a3d38d83311b63686a2379c3321194e538ff840
ms.sourcegitcommit: 66e74e39f44dca8c41f97f05528b8f9eb1aaed87
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061326"
---
# <a name="whats-new-in-this-edition"></a>此版本的新增功能

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Microsoft Outlook MAPI 参考已更新为包含各种新功能的文档。 
  
## <a name="new-content"></a>新内容

已针对以下功能添加了内容：
  
- Outlook [2013 MAPI](getting-started-with-the-outlook-mapi-reference.md)参考入门主题已更新，以引用有关 Outlook 和 MAPI 功能的编程模型的综合信息，以帮助您确定最适合您需求的 API 和技术。 以下主题中还修订了指向引用的技术文章的链接： 
    
  - [Outlook MAPI 引用](outlook-mapi-reference.md)
    
  - [Outlook MAPI 引用概述](outlook-mapi-reference-overview.md)
    
- **邮件存储提供程序示例**- 包装的 [PST](message-store-provider-sample.md)存储提供程序示例代码现已修订，以识别和适应 Outlook 2013。 有关详细信息，请参阅本主题中的之前修订的内容。 
    
- **Autocomplete Stream**—The [Nickname cache](nickname-cache.md) topic， formerly **the Nk2 File Format**， had been updated to reflect changes in Outlook 2013 as well as Outlook 2010. 以下主题现已修订，提供有关 Microsoft Outlook 2003/Microsoft Office Outlook 2007 和二进制文件分析的 .nk2 文件格式开发人员准则的信息。 有关详细信息，请参阅本主题中的之前修订的内容。
    
  - [MAPI 配置文件](mapi-profiles.md)
    
  - [别名缓存](nickname-cache.md)
    
  - [自动完成 Stream](autocomplete-stream.md)
    
- **Interfaces**- [IAddrBook：：OpenEntry](iaddrbook-openentry.md) 主题记录打开通讯簿条目并返回指向用于访问该条目的接口的指针的方法。 它之前包含  *ulFlags*  参数 **MAPI_GAL_ONLY** 中的一个标志，该标志可用于打开全局地址列表 (GAL) ，并且已修改为包括其定义。
    
- **属性**- **PR_CONVERSATION_KEY** [PidTagConversationKey](pidtagconversationkey-canonical-property.md) (规范属性"主题) 命名属性与 **IPM 相关。MessageManager** 邮件Outlook MAPI。 已修订以下与 TNEF 流Transport-Neutral封装 (格式) 相关的主题： 
    
  - [将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
    
  - [将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)
    
  - [TNEF 属性到 MAPI 属性的映射](mapping-of-tnef-attributes-to-mapi-properties.md)
    
  - [attConversationID and attParentID](attconversationid-and-attparentid.md)
  
## <a name="mapi-initialization-monitor"></a>MAPI 初始化监视器  

- 有时，使用 MAPI 的应用程序可能想要知道初始化何时完成。 例如，它有多个线程，这些线程可以初始化 MAPI，或者为了响应正在初始化的 MAPI，应用程序希望执行一些工作，但不希望始终旋转 MAPI 堆栈。  初始化监视器通过从 (导出的函数OLMAPI32.DLL) 和下面介绍的一些简单接口提供此功能。 

### <a name="hresult-stdapicalltype-createmapiinitializationmonitorimapiinitmonitor-ppinitmonitor"></a>HRESULT STDAPICALLTYPE CreateMapiInitializationMonitor (IMAPIInitMonitor ppInitMonitor)  

- 这是从 OLMAPI32.DLL导出的入口点，这允许调用方检索接口以查询当前初始化状态、设置回调以完成初始化或阻止当前线程，直到完成。  从此 API 返回的对象可重用且线程安全，并且可以从任何线程调用，而不只是从检索它的线程调用。  此外，与 MAPI 公开的其他对象不同，只要加载 DLL，此对象就有效，它可以跨初始化会话重新使用，并且可在调用 MAPIInitialize 之前或之后使用。 通过 COM 标准 HRESULT 返回成功或失败，并将 out 参数分配给 IMAPIInitMonitor 的实例。 

### <a name="interface-imapiinitmonitor"></a>接口：IMAPIInitMonitor 

**IFACEMETHODIMP_ (ISInitialized) BOOL ()**
- 返回 MAPI 初始化的当前状态 

**IFACEMETHODIMP wait (DWORD timeout)**
- 在此线程上启动 BLOCKING 调用，该调用将在指定的毫秒数已过或 MAPI 已初始化时返回。  INFINITE 可用于无限等待。 

**IFACEMETHODIMP BeginWait (DWORD 超时，IMAPIWaitResult ppResult)**
- 开始等待 MAPI 初始化或经过的指定毫秒数。   这将返回 IMAPIWaitResult 接口，该接口应调用"End"，以便开始等待。  这允许调用方控制我们在等待时被阻止的线程。 

### <a name="interface-imapiwaitresult"></a>接口 IMAPIWaitResult
**IFACEMETHODIMP end () 替代**
- 调用 它以在调用它的线程上启动阻止等待，不需要是调用"BeginWait"的同一线程。 

    
## <a name="previously-revised-content"></a>以前修改过的内容

内容已添加到 MAPI 参考之前Outlook MAPI 参考中，用于以下功能：
  
- Microsoft Outlook 2013支持并行和即点即用等非传统部署方案。 这些方案会使用于加载正确 MAPI 库的逻辑复杂化。 MAPI 开发人员现在可以选择显式链接到 MAPI 函数，并且可以选择显式链接到默认 MAPI 客户端 (例如 Msmapi32.dll 的 Outlook) 的 MAPI 存根，而无需通过 MAPI 库和 Windows MAPI 存根。 有关与隐式链接相比的显式链接详细信息，请参阅 [链接到 MAPI 函数](how-to-link-to-mapi-functions.md)。 [在 CodePlex](https://mapistublibrary.codeplex.com/)网站上发布 **MAPI 存** 根库提供了 Mapi32.lib 的下拉列表替换，它支持生成 32 位和 64 位 MAPI 应用程序。 
    
- **支持 64 位 Microsoft Outlook**- 已更新适用于 API 元素的参考主题，以与支持 64 位版本的新头文件Outlook。 可从以下位置下载这些头文件[：mapI Outlook 2010：MAPI 头文件](https://www.microsoft.com/downloads/details.aspx?FamilyID=f8d01fc8-f7b5-4228-baa3-817488a66db1)。 Check [the Version of Outlook](how-to-check-the-version-of-outlook.md)中提供了一个新代码示例，用于显示如何检查安装的 Outlook 版本是否是 64 位 Microsoft Outlook 2010并且已针对 Outlook 2013 进行了修改。 如果现有的 32 位 MAPI 应用程序将在安装了 64 位 Outlook 的 64 位操作系统上运行，则需要将 32 位应用程序重新生成为 64 位应用程序。 有关 64 位和 64 位平台的 MAPI 支持Outlook，请参阅在 32 位和[64 位平台上构建 MAPI 应用程序](building-mapi-applications-on-32-bit-and-64-bit-platforms.md)。
    
- **邮件存储提供程序示例**- [示例封装 PST](message-store-provider-sample.md) 存储提供程序之前已更新以支持 64 位体系结构。 该示例的 [Initializing a Wrapped PST Store Provider](initializing-a-wrapped-pst-store-provider.md) 主题现已扩展为提供有关"封装的 PST 和 Unicode 路径"的信息。 
    
- **Autocomplete Stream** [—The Nickname cache](nickname-cache.md) topic， formerly the **Nk2 File Format**， has been updated to reflect changes in Outlook 2013 as well as Outlook 2010. 诸如自动完成列表（即用户撰写电子邮件时在"收件人"、"抄送"和"密件抄送"编辑框中显示的名称列表）的信息现在保存到本地计算机上邮件的"自动完成流"中，而不是像 Outlook 2007 中一样保存到文件中。 [](autocomplete-stream.md) 
    
  - 与自动完成流交互
    
  - 加载自动完成流
    
  - 保存自动完成流
    
- **对 MAPI 客户端的快速** 关闭支持 - MAPI 客户端现在可以启动快速关闭，让 MAPI 子系统通知加载的提供程序，以最大限度地减少快速关闭导致的数据损失。 为客户端和提供程序添加了其他接口以支持快速关闭。 有关快速关闭详细信息，请参阅 [MAPI 中的客户端关闭](client-shutdown-in-mapi.md)。
    
- **项目字段定义的** 流Outlook — 已添加 [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性的二进制流文档。 此属性指定自定义项的内置字段的所有自定义字段和数据绑定Outlook设置。 
    
- **个人存储替代**— 添加了以下接口及其各自的方法以支持覆盖 PST 存储提供程序 **PSTDisableGrow** 策略 (PST) 文件夹文件： 
    
    [IPSTOVERRIDEREQ：：IUnknown](ipstoverridereqiunknown.md)
    
    [IPSTOVERRIDE1：：IUnknown](ipstoverride1iunknown.md)
    
- **使用多个Exchange** 帐户 — 已添加 [MAPI 通讯簿 API](using-multiple-exchange-accounts.md)的文档。 此 API 已增强，支持 Exchange 中的多个 Microsoft Outlook 2010 帐户，现在Microsoft Outlook 2013。 若要正确解析多个 Exchange 帐户的地址，请使用采用帐户上下文的新函数，以便对通讯簿的调用搜索正确的 Exchange 帐户。 
    
- **MAPI 文件格式**- MAPI 配置信息已扩展，以说明如何在 [MapiSvc.inf](registering-services-and-service-providers-in-mapisvc-inf.md)中注册服务和服务提供程序中使用这些路径。
    
- **属性**- 除了有关之前添加的 38 个其他标记属性和命名属性的文档之外，还添加了以下带标记的属性：
    
  - [PidTagAddressBookChooseDirectoryAutomatically](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md)
    
  - [PidTagAssociatedSharingProvider](pidtagassociatedsharingprovider-canonical-property.md)
    
  - [PidTagRoamingBinary](pidtagroamingbinary-canonical-property.md)
    
  - [PidTagSenderSmtpAddress](pidtagsendersmtpaddress-canonical-property.md)
    
  - [PidTagSentRepresentingSmtpAddress](pidtagsentrepresentingsmtpaddress-canonical-property.md)
    
  - [PidTagStoreEntryIdEmsmdbV1](pidtagstoreentryidemsmdbv1-canonical-property.md)
    
- **MAPI 常量**- 合并 [的 MAPI](mapi-constants.md) 常量已展开。 在以前的版本中，它们分发到许多主题中，但现在收集在单个主题中，以便更轻松地发现和使用它们。 它们还进行了扩展以提供更广泛的覆盖范围，包括以下部分： 
    
  - 通讯簿Exchange邮件存储错误代码的定义
    
  - 邮箱缓存Exchange Server配额的定义
    
## <a name="see-also"></a>另请参阅



[Outlook MAPI 引用入门](getting-started-with-the-outlook-mapi-reference.md)
  
[CodePlex](https://mapistublibrary.codeplex.com/)

