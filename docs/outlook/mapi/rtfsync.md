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
ms.openlocfilehash: f6afa890f61bb2f394e3cf69e0f2c54699a2ad9e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778670"
---
# <a name="rtfsync"></a>RTFSync

**适用于**： Outlook 
  
确保富文本格式 (RTF) 消息文本匹配的纯文本版本。 有必要阅读 RTF 版本之前和之后修改的 RTF 版本调用此函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |RTF 感知客户端应用程序和消息存储提供程序  <br/> |
   
```cpp
HRESULT RTFSync(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  BOOL FAR * lpfMessageUpdated
);
```

## <a name="parameters"></a>参数

_lpMessage_
  
> [in]指向要更新的消息的指针。
    
_ulFlags_
  
> [in]已更改的用于指示 RTF 或纯文本邮件版本标志位掩码。 可以设置以下标志：
    
  - RTF_SYNC_BODY_CHANGED： 已更改邮件的纯文本版本。
      
  - RTF_SYNC_RTF_CHANGED： 邮件的 RTF 版本已更改。
    
  _UlFlags_参数中的所有其他位保留以供将来使用。 
    
_lpfMessageUpdated_
  
> [输出]指向指示是否已更新的消息的变量的指针。 如果没有，则更新的消息，则返回 FALSE 否则，则为 TRUE。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

如果**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性缺失或为 FALSE，然后才能调用读取**RTFSync**函数的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性，应已 RTF_SYNC_BODY_更改设置标志。 
  
如果**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中未设置 STORE_RTF_OK 标志，应使用 RTF_SYNC_RTF_CHANGED 标志设置修改**PR_RTF_COMPRESSED**后调用此函数。 
  
如果**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 和**PR_RTF_COMPRESSED**已更改，应设置这两个 flags 调用**RTFSync**函数。 
  
如果_lpfMessageUpdated_参数的值设置为 TRUE，则应为邮件调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。 如果未调用**SaveChanges** ，消息中将不保存所做的修改。 
  
消息存储提供程序可以使用**RTFSync**保持同步的**PR_BODY**和**PR_RTF_COMPRESSED**属性。 
  
有关详细信息，请参阅[消息存储提供程序支持 RTF 的文本](supporting-rtf-text-for-message-store-providers.md)。 
  
## <a name="see-also"></a>另请参阅

- [WrapCompressedRTFStream](wrapcompressedrtfstream.md)

