---
title: IMAPIFormGetViewContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.GetViewContext
api_type:
- COM
ms.assetid: c6938986-a9f9-4ef4-9655-ded55b7357db
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2c463252aa029ac4c7cb2fac6e962a5d8af31b97
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775371"
---
# <a name="imapiformgetviewcontext"></a>IMAPIForm::GetViewContext

  
  
**适用于**： Outlook 
  
返回表单的当前视图上下文。 
  
```cpp
HRESULT GetViewContext(
  LPMAPIVIEWCONTEXT FAR * ppViewContext
);
```

## <a name="parameters"></a>参数

 _ppViewContext_
  
> [输出]指向到窗体的视图上下文的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回窗体的当前视图上下文。 
    
S_FALSE 
  
> 没有窗体视图上下文。
    
## <a name="remarks"></a>说明

表单查看器调用**GetViewContext**以获取视图上下文中向[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)以前呼叫建立的指针。 如果对**SetViewContext**不进行了任何以前的呼叫， **GetViewContext**将_ppViewContext_设置为 NULL。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

将窗体的视图上下文指针复制到传入呼叫的窗体查看_ppViewContext_参数中的指针。 如果表单没有了视图上下文，设置为 NULL _ppViewContext_ 。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |OpenMessageNonModal  <br/> |MFCMAPI 使用**IMAPIForm::GetViewContext**方法来检查窗体是否有了视图上下文。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

