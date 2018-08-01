---
title: Outlook MAPI 引用概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4c126d0c-d7c0-45c0-801c-c9f1e44c9db6
description: 上次修改时间： 2013 年 2 月 1 日
ms.openlocfilehash: c0d7faaa957167977606cd93800a085d62b214f5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776569"
---
# <a name="outlook-mapi-reference-overview"></a>Outlook MAPI 引用概述

**适用于**： Outlook 
  
本主题提供有关 Outlook 2013 MAPI 参考文档的概述信息。
  
## <a name="about-this-documentation"></a>关于本文档

本文档适用于实现的消息处理 API (MAPI) Microsoft Outlook 2013 中。 
  
Microsoft Office Outlook 2007，之前 MAPI 程序员参考是 Microsoft Exchange 文档的一部分。
  
> [!NOTE]
> 由于 Exchange 具有 Microsoft Exchange Server 2007 以来 deemphasized 使用 MAPI，支持的 Exchange 实施是有限。 
  
与 Microsoft Exchange 实现不同的 MAPI Outlook 实现。 Outlook 实现专为客户端计算机上运行并强调低延迟。 Exchange 实施供服务器其中高可用性和更多线程重要。
  
在最终用户系统上运行的应用程序使用本文档。 服务器应用程序，使用 MAPI 如果合适，Exchange 实现或使用如 Exchange Web 服务的当前 Exchange Api。 Exchange Web 服务的详细信息，请参阅[Exchange Web 服务引用](http://msdn.microsoft.com/en-us/library/bb204119.aspx)。
  
它可能可以编写使用 Outlook 或 Exchange 实现的 MAPI 的应用程序。 例如，MFCMAPI 也在任一平台上工作。 实现具有许多常见的功能，但有区别明显和不明显。 您将需要如果您希望您的应用程序，在所有的环境中工作，仔细测试这两个平台上。 此测试将需要两个系统，因为不支持运行于同一操作系统安装的两个实现。
  
请注意，MAPI 适合低级别访问 MAPI 存储区中的数据或构建传输、 消息存储库或通讯簿提供程序。 MAPI 绕过 Outlook 的业务逻辑，因为您还应考虑使用 Outlook 对象模型，用于生成您的解决方案评估 Api 时。 Outlook 对象模型执行封装 Outlook 业务逻辑，但不适用于多线程的代码、 同步提供程序或 Windows 服务应用程序。
  
有关此版本中新增的信息，请参阅以下主题：
  
- [此版本的新增功能](what-s-new-in-this-edition.md)
    
- [在此版本中弃用的 API 元素](api-elements-deprecated-in-this-edition.md)
    
如果您是新开发面向 Outlook 的 MAPI 应用程序，请参阅以下主题：
  
- [选择的 API 或技术来开发解决方案的 Outlook 2013](http://msdn.microsoft.com/en-us/library/jj900714.aspx)
    
- [常用头文件](commonly-used-header-files.md)
    
- [常用属性](commonly-used-properties.md)
    
- [常用对象](commonly-used-objects.md)
    
此参考的其余部分分为以下三种类型的信息：
  
- [MAPI 示例](mapi-samples.md)-将您定向到显示各种 API 元素以及如何实现基本 MAPI 提供程序和创建 Outlook 项目使用的多个代码示例。 
    
- [MAPI 概念](mapi-concepts.md)-介绍的概念和体系结构的 MAPI。 
    
- [MAPI 参考](mapi-reference.md)-提供有关函数、 接口、 结构和 MAPI 中的属性的详细的信息。 
    
## <a name="see-also"></a>另请参阅

- [Outlook MAPI 引用入门](getting-started-with-the-outlook-mapi-reference.md)
- [MAPI 示例（英文）](mapi-samples.md)
- [MAPI 概念](mapi-concepts.md)

