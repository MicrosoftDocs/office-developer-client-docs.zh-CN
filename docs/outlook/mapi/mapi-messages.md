---
title: MAPI 邮件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 417c113f-bd98-4515-85d1-09db7fc3a227
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1146fa0441d0b55a7610368324489bd3a6bb24e1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776269"
---
# <a name="mapi-messages"></a>MAPI 邮件

  
  
**适用于**： Outlook 
  
邮件是传输到另一个通过 MAPI 后台处理程序和服务提供商通过邮件系统的一台客户端应用程序的 MAPI 对象。 MAPI 中的几乎在每个组件处理的邮件。 客户端让用户创建、 保存、 发送和删除此外，复制并将其从一个文件夹移动到另一个邮件。 消息存储提供程序负责为邮件管理和邮件传递到 MAPI 后台处理程序或传输提供程序。 MAPI 后台处理程序会将邮件移动到适当的传输提供程序，而传输提供程序处理的传送和接收邮件与邮件系统，然后设置收件人和消息选项属性。 通讯簿提供程序处理间接邮件，支持描述邮件收件人的属性。
  
消息存储在整个邮件存储区中，通常人际邮件 (IPM) 根文件夹中创建的文件夹的文件夹中。 邮件通常存储在相同的级别标准 IPM 收件箱、 已发送邮件、 已删除邮件和发件箱文件夹或层次结构中的较低级别。 但是，也可以 IPM 子树外部存储消息。
  
在标准 IPM 子树中创建的邮件都具有标准内容 （即，对客户端应用程序的用户可见的内容）。 注释和报告是具有标准内容的邮件的示例。 消息也可以创建与关联的内容或在典型的客户端中不可见的内容。 文件夹支持两个不同内容表来保存不同类型的邮件： 一种标准内容的标准邮件和关联邮件关联的内容表。 MAPI 不设置关联的消息的内容的标准，因为它们可包含任意信息。 
  
指定在邮件有其他数据 — 的文件，另一条消息或 OLE 对象形式 — 与之关联。 此附加的数据，该数据库称为附件，显示为图标或，RTF 邮件，为图元文件消息文本中。 零、 一个或多个附件，可以有一条消息。 始终为邮件传输附件。
  
传输邮件有一个或多个收件人 （与特定的邮件系统关联的地址）。 某些收件人的通讯簿提供程序中的当前配置文件; 所属的容器中的条目创建其他收件人仅将邮件传输。 由于必须通过关联它们是邮件访问收件人和附件，邮件的收件人和附件称为及其子对象。 
  
消息存储提供程序支持通过中三个接口方法的邮件、 附件和收件人： 
  
|**接口**|**说明**|
|:-----|:-----|
|[IMessage](imessageimapiprop.md) <br/> |管理附件和收件人发送邮件、 设置读取的状态。  <br/> |
|[IMAPIFolder](imapifolderimapicontainer.md) <br/> |创建、 复制，并将移动消息和子文件夹和管理邮件状态。  <br/> |
|[IAttach](iattachimapiprop.md) <br/> |管理附件属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 应用程序开发](mapi-application-development.md)

