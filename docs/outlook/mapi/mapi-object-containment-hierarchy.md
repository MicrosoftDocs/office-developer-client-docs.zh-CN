---
title: MAPI 对象包含层次结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 33747835-6eeb-4e07-8f92-3cfa81eecd0f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f5faf3a3d4971b01509d0ff0cfa59451015ba205
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426924"
---
# <a name="mapi-object-containment-hierarchy"></a>MAPI 对象包含层次结构
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对象之间的包含关系指定某些对象对于访问的其他对象具有的依赖关系。 对于客户端应用程序，通过访问特定对象，可以访问其他对象。 在某些情况下，服务提供商实现的对象之间的包含关系遵循逻辑层次结构。 在其他情形下，它是任意的。 
  
客户端必须先获取对 MAPI 会话对象的访问权限，然后才能使用许多其他对象 (例如，服务提供商和 MAPI 通讯簿) 。
  
邮件存储包含基于邮件存储中的对象之间的分层关系：邮件存储对象本身、文件夹、邮件和附件。 在逻辑上，附件包含在邮件、文件夹中的邮件和邮件存储中的文件夹中。 包含关系匹配此逻辑层次结构。 例如，要获取对邮件的访问权限，客户端必须先访问包含邮件的文件夹。 配置文件和 status 对象是更为任意的包含关系的示例。 这两个对象都可以通过会话使用。 
  
对于一些对象，容器仅提供访问权限。 附件和收件人是完全依赖于其容器的对象示例。 对附件或收件人的唯一访问权限是通过附件或收件人所属的邮件。 其他对象具有备用访问路径。 这些对象由创建它们的服务提供程序分配二进制标识符（称为条目标识符）。 条目标识符可用于直接访问其对象，从而使客户端可以绕过包含树。 
  
下图显示了 MAPI 包含层次结构。 会话位于树的顶部，因为客户端通过会话获得对所有其他对象的访问。 下一个级别包括邮件存储表、列出当前会话中所有邮件存储提供程序的属性的表对象以及提供访问所有通讯簿提供程序的通讯簿。 邮件存储表和通讯簿用于访问由特定服务提供程序实现的对象，如下图所示，以包含顺序显示。
  
**MAPI 包容层次结构**
  
![MAPI 包含层次结构](media/amapi_41.gif "MAPI 包含层次结构")
  
## <a name="see-also"></a>另请参阅

- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

