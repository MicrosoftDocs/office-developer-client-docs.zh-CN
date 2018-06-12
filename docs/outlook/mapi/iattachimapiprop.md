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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 66e318c3b7b772f2713b5c730590ce4a8ad5965b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775256"
---
# <a name="iattach--imapiprop"></a>IAttach: IMAPIProp

  
  
**适用于**： Outlook 
  
维护并提供对属性的邮件中的附件的访问。 **IAttach**接口都有其自己的方法都不唯一。 有关如何使用附件的详细信息，请参阅[MAPI 附件](mapi-attachments.md)和[附件表](attachment-tables.md)。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |Attachment 对象  <br/> |
|通过实现：  <br/> |消息存储提供程序  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IAttachment  <br/> |
|指针类型：  <br/> |LPATTACH  <br/> |
|事务模型：  <br/> |事务处理  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

此接口不具有任何唯一的方法。
  
|**必需的属性**|**访问**|
|:-----|:-----|
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_ATTACH_METHOD**([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_RENDERING_POSITION**([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))  <br/> |读/写  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

