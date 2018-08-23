---
title: IMAPIMessageSiteGetStore
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetStore
api_type:
- COM
ms.assetid: d1ca619e-8bdc-417b-aed6-23dd30e6eafa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1f4e6c49ca1c537f78ccce708c4a0b00f81ad7e4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567928"
---
# <a name="imapimessagesitegetstore"></a>IMAPIMessageSite::GetStore

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
如果存在此类存储，返回包含当前邮件的邮件存储区。 此方法将返回 NULL 中嵌入的邮件，而不是直接在消息存储库中的其他邮件中存储的_ppStore_参数。 
  
```cpp
HRESULT GetStore(
  LPMDB FAR * ppStore
);
```

## <a name="parameters"></a>参数

 _ppStore_
  
> [输出]指向消息存储的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
S_FALSE 
  
> 包含邮件没有存储区。
    
## <a name="remarks"></a>注解

有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::GetStore  <br/> |MFCMAPI 使用**IMAPIMessageSite::GetStore**方法来获取当前缓存的指针到指定的存储，它是否可用。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

