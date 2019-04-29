---
title: MAPI 会话处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3bc4aea5-ab01-4ba5-a4ad-7a9a76c6bf55
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 98c4bd0dba630db32fdb2309be3d29ebc13b1131
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422059"
---
# <a name="mapi-session-handling"></a>MAPI 会话处理

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
您必须先建立会话, 然后才能与服务提供商和基础邮件系统通信。 MAPI 会话是从客户端到其他 MAPI 组件的链接。 成功启动会话后, MAPI 将向客户端返回一个指向 session 对象的指针, 该对象是一个实现**IMAPISession**接口的对象。 有关详细信息, 请参阅[IMAPISession: IUnknown](imapisessioniunknown.md)。 您可以使用**IMAPISession**接口的方法来访问通讯簿和邮件存储提供程序的对象、访问多个表、显示表单、设置传输提供程序属性, 以及执行配置文件和邮件服务管理。 
  
## <a name="in-this-section"></a>本节内容

[启动 MAPI 会话](starting-a-mapi-session.md)
  
> 介绍如何启动 MAPI 会话并包含指向更详细信息的主题的链接。
    
[结束 MAPI 会话](ending-a-mapi-session.md)
  
> 介绍如何结束 MAPI 会话。
    
[使用会话访问对象](accessing-objects-by-using-the-session.md)
  
> 介绍如何使用会话指针访问 session 对象。
    
[检索主标识和提供程序标识](retrieving-primary-and-provider-identity.md)
  
> 介绍用于检索主标识和提供程序标识的属性。
    
[状态表和状态对象](status-table-and-status-objects.md)
  
> 介绍如何访问状态表中的信息。
    

