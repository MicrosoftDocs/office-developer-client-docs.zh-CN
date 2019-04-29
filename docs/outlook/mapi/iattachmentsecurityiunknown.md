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
  
允许使用 microsoft outlook 2010 和 microsoft outlook 2013 解决方案查看附件是否被视为不安全, 并在查看和编制索引时被阻止。
  
|||
|:-----|:-----|
|接口标识符:  <br/> |IID_IAttachmentSecurity  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[IAttachmentSecurity::IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md) <br/> |检查指定的附件是否被 outlook 2010 或 outlook 2013 阻止, 以供查看和编制索引。  <br/> |
   
## <a name="remarks"></a>说明

outlook 2010 和 outlook 2013 解决方案可以查询此接口, 以查看是否阻止了附件。 outlook 2010 或 outlook 2013 阻止的附件根据 outlook 2010 或 outlook 2013 的配置方式以及管理员已应用的策略的不同而有所不同。
  
## <a name="see-also"></a>另请参阅



[MAPI 常量](mapi-constants.md)
  
[验证附件是否已被阻止](how-to-verify-an-attachment-is-blocked.md)

