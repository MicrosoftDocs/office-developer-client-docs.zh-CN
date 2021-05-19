---
title: IMAPIViewContextSetAdviseSink
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.SetAdviseSink
api_type:
- COM
ms.assetid: 4799084a-b5d1-48c3-a889-b2f0e9d68c30
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7ee641214e1eaae667af356fd8dbe51ff7dc7982
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419392"
---
# <a name="imapiviewcontextsetadvisesink"></a>IMAPIViewContext::SetAdviseSink

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
管理表单的注册以接收有关查看器中更改的通知。 
  
```cpp
HRESULT SetAdviseSink(
LPMAPIFORMADVISESINK pmvns
);
```

## <a name="parameters"></a>参数

 _pmvns_
  
> [in]指向窗体的指针建议接收对象或 NULL。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单通知的注册或取消成功。
    
## <a name="remarks"></a>备注

Form 对象调用 **IMAPIViewContext：：SetAdviseSink** 方法，以注册以了解表单查看器中的更改或取消以前的注册。 当  _pmvns_ 设置为 NULL 时，表单想要取消注册。 当  _pmvns_ 指向有效的表单通知接收器时，表单想要注册将来通知。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

当 **SetAdviseSink** 包含窗体通知接收器指针时，请保留对它的引用，直到进行另一个 **SetAdviseSink** 调用以取消通知。 在查看器中发生更改时以及加载新邮件时发送通知。 
  
有关详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：SetAdviseSink  <br/> |MFCMAPI 在此函数中实现 **IMAPIViewContext：：SetAdviseSink** 方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

