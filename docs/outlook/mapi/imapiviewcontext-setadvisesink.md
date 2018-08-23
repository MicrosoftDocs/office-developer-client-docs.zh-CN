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
ms.openlocfilehash: 555bb4820dc36934fb28197b7e222633a5248125
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583181"
---
# <a name="imapiviewcontextsetadvisesink"></a>IMAPIViewContext::SetAdviseSink

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
管理窗体的注册中查看者接收有关更改的通知。 
  
```cpp
HRESULT SetAdviseSink(
LPMAPIFORMADVISESINK pmvns
);
```

## <a name="parameters"></a>参数

 _pmvns_
  
> [in]向窗体的指针建议接收器对象或 NULL。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功注册或取消的窗体通知。
    
## <a name="remarks"></a>注解

表单对象调用任一注册，以了解有关表单查看器中更改或取消预先注册到**IMAPIViewContext::SetAdviseSink**方法。 当_pmvns_设置为 NULL 时，表单想要取消注册。 时有效的窗体的_pmvns_指向告知接收器，窗体想要注册将来的通知。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果**SetAdviseSink**包含窗体告知接收器指针，请继续对它的引用，直到进行另一个**SetAdviseSink**调用取消通知。 在您查看器和所加载新消息时，将发生更改时发送通知。 
  
有关详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::SetAdviseSink  <br/> |MFCMAPI 此函数中实现**IMAPIViewContext::SetAdviseSink**方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

