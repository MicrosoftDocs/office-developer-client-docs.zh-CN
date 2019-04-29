---
title: RTFSync
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- RTFSync
api_type:
- HeaderDef
ms.assetid: 627f95e9-39ac-4d43-8f02-687783b09785
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dfdf1068caaab3894b1b489d53ccc8debe1b3a29
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436207"
---
# <a name="rtfsync"></a>RTFSync

**适用于**：Outlook 2013 | Outlook 2016 
  
确保 rtf 格式 (rtf) 邮件文本与纯文本版本相匹配。 在阅读 rtf 版本和修改 rtf 版本之后, 必须调用此函数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |RTF 感知客户端应用程序和邮件存储提供程序  <br/> |
   
```cpp
HRESULT RTFSync(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  BOOL FAR * lpfMessageUpdated
);
```

## <a name="parameters"></a>参数

_lpMessage_
  
> 实时指向要更新的邮件的指针。
    
_ulFlags_
  
> 实时标记的位掩码, 用于指示邮件的 RTF 或纯文本版本已更改。 可以设置以下标志:
    
  - RTF_SYNC_BODY_CHANGED: 邮件的纯文本版本已更改。
      
  - RTF_SYNC_RTF_CHANGED: 邮件的 RTF 版本已更改。
    
  _ulFlags_参数中的其他所有位都将保留以供将来使用。 
    
_lpfMessageUpdated_
  
> 排除指向一个变量的指针, 该变量指示是否有更新的邮件。 如果有更新的邮件, 则为 TRUE, 否则为 FALSE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

如果**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性缺失或为 FALSE, 则在读取**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性之前, 应使用 RTFSync 调用**RTF_SYNC_BODY_** 函数已更改的标志集。 
  
如果**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中未设置 STORE_RTF_OK 标志, 则应在修改**PR_RTF_COMPRESSED**后设置 RTF_SYNC_RTF_CHANGED 标志来调用此函数。 
  
如果同时更改了**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 和**PR_RTF_COMPRESSED** , 则应使用这两个标志集调用**RTFSync**函数。 
  
如果将_lpfMessageUpdated_参数的值设置为 TRUE, 则应为邮件调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法。 如果未调用**SaveChanges** , 修改将不会保存在邮件中。 
  
邮件存储提供程序可以使用**RTFSync**保持**PR_BODY**和**PR_RTF_COMPRESSED**属性同步。 
  
有关详细信息, 请参阅[支持邮件存储提供程序的 RTF 文本](supporting-rtf-text-for-message-store-providers.md)。 
  
## <a name="see-also"></a>另请参阅

- [WrapCompressedRTFStream](wrapcompressedrtfstream.md)

