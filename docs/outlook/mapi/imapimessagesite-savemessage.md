---
title: IMAPIMessageSiteSaveMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.SaveMessage
api_type:
- COM
ms.assetid: 94c44952-d297-4705-9778-90373dfa5ad6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 938eaa6c1a39d24157d5d690c42b435af6192cb6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417103"
---
# <a name="imapimessagesitesavemessage"></a>IMAPIMessageSite::SaveMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
请求保存当前邮件。
  
```cpp
HRESULT SaveMessage( void );
```

## <a name="parameters"></a>参数

无。
  
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。 
    
## <a name="remarks"></a>备注

表单调用 **IMAPIMessageSite：：SaveMessage** 方法来请求保存消息。 
  
有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：SaveMessage  <br/> |MFCMAPI 使用 **IMAPIMessageSite：：SaveMessage** 方法来保存邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

