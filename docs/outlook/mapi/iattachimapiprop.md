---
title: IAttach IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAttach
api_type:
- COM
ms.assetid: f47e20e1-2a30-4c9e-8ca6-e8c5e72f44a1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2ef3bc973e12bd5630cc00b3c512b748d4a16e86
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409088"
---
# <a name="iattach--imapiprop"></a>IAttach : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
维护和提供对邮件中附件属性的访问权限。 **IAttach** 接口没有其自己的唯一方法。 有关如何使用附件的信息，请参阅[MAPI Attachments](mapi-attachments.md) and [Attachment Tables。](attachment-tables.md) 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|公开者：  <br/> |Attachment 对象  <br/> |
|实现者：  <br/> |邮件存储提供程序  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IAttachment  <br/> |
|指针类型：  <br/> |LPATTACH  <br/> |
|事务模型：  <br/> |Transacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

此接口没有任何唯一的方法。
  
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |只读  <br/> |
|**PR_ATTACH_METHOD (** [PidTagAttachMethod)](pidtagattachmethod-canonical-property.md)  <br/> |读/写  <br/> |
|**PR_RENDERING_POSITION (** [PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))   <br/> |读/写  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

