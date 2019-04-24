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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329457"
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
  
> 排除指向表单的视图上下文的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回表单的当前视图上下文。 
    
S_FALSE 
  
> 没有表单的视图上下文。
    
## <a name="remarks"></a>注解

表单查看者调用**GetViewContext**以获取指向在之前调用[IMAPIForm:: SetViewContext](imapiform-setviewcontext.md)时建立的视图上下文的指针。 如果之前未对**SetViewContext**进行任何调用, 则**GetViewContext**会将_ppViewContext_设置为 NULL。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

将表单的视图上下文指针复制到由_ppViewContext_参数中的调用表单查看器传入的指针中。 如果窗体没有视图上下文, 则将_ppViewContext_设置为 NULL。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions  <br/> |OpenMessageNonModal  <br/> |MFCMAPI 使用**IMAPIForm:: GetViewContext**方法检查窗体中是否有视图上下文。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

