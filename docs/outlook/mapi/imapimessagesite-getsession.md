---
title: IMAPIMessageSiteGetSession
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetSession
api_type:
- COM
ms.assetid: c35d9e38-f4cf-4908-aaa1-a4263b58f7e8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e1ea68a7690a93915cd80ad5406c4d71d3a97400
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412686"
---
# <a name="imapimessagesitegetsession"></a>IMAPIMessageSite::GetSession

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回在其中创建或打开当前邮件的 MAPI 会话。
  
```cpp
HRESULT GetSession(
  LPMAPISESSION FAR * ppSession
);
```

## <a name="parameters"></a>参数

 _ppSession_
  
> 排除指向指向返回的 session 对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
S_FALSE 
  
> 当前邮件不存在会话。
    
## <a name="remarks"></a>说明

有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer  <br/> |CMyMAPIFormViewer:: GetSession  <br/> |MFCMAPI 使用**IMAPIMessageSite:: GetSession**方法返回当前缓存的会话指针 (如果可用)。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

