---
title: 邮件存储提供程序的结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 064b2fc1-e690-43e6-95d3-a61438115de5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: eda62a4cd31e0de695d52391a6717e7a0f5ea581
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426420"
---
# <a name="structure-of-message-store-providers"></a>邮件存储提供程序的结构
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当邮件存储提供程序在内存中运行时, 它是[IMSProvider: IUnknown](imsprovideriunknown.md)接口。 **IMSProvider**接口允许客户端应用程序和 MAPI 后台处理程序登录和注销邮件存储区。 客户端应用程序和 MAPI 后台处理程序用于访问邮件存储区中的文件夹和邮件的接口为[IMSLogon](imslogoniunknown.md)和[IMsgStore](imsgstoreimapiprop.md)接口。 这些接口通常是在邮件存储区首次登录时创建的, 尽管邮件存储 DLL 的[MSProviderInit](msproviderinit.md)入口点也可以创建这些接口。 
  
由于**IMSLogon**和**IMsgStore**接口共享某些方法, 因此创建一个从这两个接口继承的类对象可能会更简单。 您还可以在单独的对象中实现这些接口, 并在 DLL 内部编写 helper 函数, 以实现可从**IMSLogon**和**IMsgStore**接口中的方法调用的共享方法。 
  
下图显示了正在运行的邮件存储区中的对象层次结构的高级大纲。
  
**消息存储对象层次结构**
  
![邮件存储对象层次结构](media/storeobj.gif "邮件存储对象层次结构")
  
## <a name="see-also"></a>另请参阅

- [开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

