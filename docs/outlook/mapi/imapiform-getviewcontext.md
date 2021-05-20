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
ms.openlocfilehash: f0b217372f6b4848f83c993846cd08a81c7098e8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430901"
---
# <a name="imapiformgetviewcontext"></a>IMAPIForm::GetViewContext

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回窗体的当前视图上下文。 
  
```cpp
HRESULT GetViewContext(
  LPMAPIVIEWCONTEXT FAR * ppViewContext
);
```

## <a name="parameters"></a>参数

 _ppViewContext_
  
> [out]指向指向表单视图上下文的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回表单的当前视图上下文。 
    
S_FALSE 
  
> 没有表单的视图上下文。
    
## <a name="remarks"></a>备注

表单查看器调用 **GetViewContext** 以获取指向在上一次调用 [IMAPIForm：：SetViewContext 时建立的视图上下文的指针](imapiform-setviewcontext.md)。 如果没有事先调用 **SetViewContext** **，GetViewContext** 将  _ppViewContext_ 设置为 NULL 。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

将表单的视图上下文指针复制到由调用表单查看器在  _ppViewContext_ 参数中传递的指针。 如果表单没有视图上下文，则将  _ppViewContext_ 设置为 NULL。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |OpenMessageNonModal  <br/> |MFCMAPI 使用 **IMAPIForm：：GetViewContext** 方法检查表单是否具有视图上下文。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

