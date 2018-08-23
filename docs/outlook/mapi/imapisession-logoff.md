---
title: IMAPISessionLogoff
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.Logoff
api_type:
- COM
ms.assetid: 93e38f6c-4b67-4f2d-bc94-631efec86852
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9dfc3b3381139b6b7fe47fb369d1cd69ee5e9677
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587836"
---
# <a name="imapisessionlogoff"></a>IMAPISession::Logoff

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
结束 MAPI 会话。
  
```cpp
HRESULT Logoff(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG ulReserved
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]父窗口的任何对话框或窗口将显示句柄。 如果未设置 MAPI_LOGOFF_UI 标志，则忽略此参数。
    
 _ulFlags_
  
> [in]控制注销操作的标志的位掩码。 可以设置以下标志：
    
MAPI_LOGOFF_SHARED 
  
> 如果共享此会话，则登录使用共享的会话的所有客户端应正在注销的通知。 客户端应注销。 使用共享的会话的任何客户端可以设置此标志。 如果不共享当前会话，则忽略 MAPI_LOGOFF_SHARED。
    
MAPI_LOGOFF_UI 
  
> **注销**可以显示一个对话框，在操作时，可能会提示用户进行确认。 
    
 _ulReserved_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注销操作已成功。
    
## <a name="remarks"></a>注解

**IMAPISession::Logoff**方法结束 MAPI 会话。 **注销**返回时，无除外[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法可调用它。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**注销**返回时，通过调用其**IUnknown::Release**方法释放会话对象。 
  
结束会话的详细信息，请参阅[结束 MAPI 会话](ending-a-mapi-session.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIObjects.cpp  <br/> |CMapiObjects::Logoff  <br/> |MFCMAPI 使用**IMAPISession::Logoff**方法从之前将其释放会话中注销。  <br/> |
   
> [!NOTE]
> 在 Microsoft Office Outlook 2007 Service Pack 2、 Microsoft Outlook 2010 和 Microsoft Outlook 2013 中引入的快速关闭行为，由于客户端应永远不会传递给[IMAPISession::Logoff](imapisession-logoff.md)的**MAPI_LOGOFF_SHARED**参数。 传递**MAPI_LOGOFF_SHARED**都将导致开始关闭所有 MAPI 客户端和出现异常的行为，则会发生。 
  
## <a name="see-also"></a>另请参阅



[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[结束 MAPI 会话](ending-a-mapi-session.md)

