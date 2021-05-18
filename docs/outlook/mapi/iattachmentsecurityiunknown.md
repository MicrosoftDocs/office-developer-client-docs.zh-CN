---
title: IAttachmentSecurity IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAttachmentSecurity
api_type:
- COM
ms.assetid: 69609f73-5884-9e2b-ab78-a2e0ece3a1d1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8464c8265ebc1754f7909be5413620e7f76db5f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411412"
---
# <a name="iattachmentsecurity--iunknown"></a>IAttachmentSecurity : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
允许Microsoft Outlook 2010和Microsoft Outlook 2013解决方案，以查明附件是否被视为不安全且被阻止查看和编制索引。
  
|||
|:-----|:-----|
|接口标识符：  <br/> |IID_IAttachmentSecurity  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[IAttachmentSecurity::IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md) <br/> |检查指定的附件是否被 2010 Outlook 2013 Outlook 2013 阻止查看和编制索引。  <br/> |
   
## <a name="remarks"></a>备注

Outlook 2010 Outlook 2013 解决方案可以查询此接口以查看附件是否被阻止。 Outlook 2010 或 Outlook 2013 阻止的附件因 Outlook 2010 或 Outlook 2013 的配置方式以及管理员应用的策略而异。
  
## <a name="see-also"></a>另请参阅



[MAPI 常量](mapi-constants.md)
  
[验证附件被阻止](how-to-verify-an-attachment-is-blocked.md)

