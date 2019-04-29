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
  
管理表单注册, 以便在查看器中接收有关更改的通知。 
  
```cpp
HRESULT SetAdviseSink(
LPMAPIFORMADVISESINK pmvns
);
```

## <a name="parameters"></a>参数

 _pmvns_
  
> 实时指向表单建议接收器对象或空值的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单通知的注册或取消已成功。
    
## <a name="remarks"></a>说明

表单对象调用**IMAPIViewContext:: SetAdviseSink**方法以注册, 以了解有关表单查看器中的更改或取消之前的注册。 当_pmvns_设置为 NULL 时, 窗体要取消注册。 当_pmvns_指向有效的窗体建议接收器时, 该表单希望注册将来的通知。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

当**SetAdviseSink**包含窗体建议接收器指针时, 保留对它的引用, 直到再次调用**SetAdviseSink**以取消通知。 在查看器中发生更改时, 以及在加载新邮件时发送通知。 
  
有关详细信息, 请参阅[发送和接收表单通知](sending-and-receiving-form-notifications.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer  <br/> |CMyMAPIFormViewer:: SetAdviseSink  <br/> |MFCMAPI 实现此函数中的**IMAPIViewContext:: SetAdviseSink**方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

