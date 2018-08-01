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
ms.openlocfilehash: 040be6cea64dd58e23d79c20a9ae9dddf02fa87d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775260"
---
# <a name="iattachmentsecurity--iunknown"></a>IAttachmentSecurity : IUnknown

  
  
**适用于**： Outlook 
  
允许 Microsoft Outlook 2010 和 Microsoft Outlook 2013 的解决方案，以找出是否附件被视为不安全的和阻止的查看和编制索引。
  
|||
|:-----|:-----|
|接口标识符：  <br/> |IID_IAttachmentSecurity  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[IAttachmentSecurity::IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md) <br/> |检查是否指定的附件阻止通过 Outlook 2010 或 Outlook 2013 的查看和编制索引。  <br/> |
   
## <a name="remarks"></a>说明

Outlook 2010 和 Outlook 2013 解决方案可以查询以确定是否阻止附件此接口。 Outlook 2010 或 Outlook 2013 被阻止的附件取决于已如何配置 Outlook 2010 或 Outlook 2013 和管理员已应用策略。
  
## <a name="see-also"></a>另请参阅



[MAPI 常量](mapi-constants.md)
  
[验证附件是否已遭阻止](how-to-verify-an-attachment-is-blocked.md)

