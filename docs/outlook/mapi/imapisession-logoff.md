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
ms.openlocfilehash: 317c3702415ddf30038ccd0d40cdf0f19abc61f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338106"
---
# <a name="imapisessionlogoff"></a>IMAPISession::Logoff

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
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
  
> 实时要显示的任何对话框或窗口的父窗口的句柄。 如果未设置 MAPI_LOGOFF_UI 标志, 则忽略此参数。
    
 _ulFlags_
  
> 实时控制注销操作的标志的位掩码。 可以设置以下标志:
    
MAPI_LOGOFF_SHARED 
  
> 如果此会话是共享的, 则应通知使用共享会话登录的所有客户端正在进行的注销。 客户端应注销。 任何使用共享会话的客户端都可以设置此标志。 如果当前会话不是共享的, 则忽略 MAPI_LOGOFF_SHARED。
    
MAPI_LOGOFF_UI 
  
> **注销**可以在操作过程中显示对话框, 可能会提示用户进行确认。 
    
 _ulReserved_
  
> 实时保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注销操作成功。
    
## <a name="remarks"></a>注解

**IMAPISession:: 注销**方法结束 MAPI 会话。 当**注销**时, 将不会调用除了[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)之外的任何方法。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当**注销**时, 请通过调用其**IUnknown:: release**方法来释放 session 对象。 
  
有关结束会话的详细信息, 请参阅[结束 MAPI 会话](ending-a-mapi-session.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIObjects  <br/> |CMapiObjects:: 注销  <br/> |MFCMAPI 使用**IMAPISession:: 注销**方法从会话中注销, 然后再将其发布。  <br/> |
   
> [!NOTE]
> 由于 microsoft Office Outlook 2007 Service Pack 2、microsoft outlook 2010 和 microsoft outlook 2013 中引入了快速关闭行为, 客户端决不应将**MAPI_LOGOFF_SHARED**参数传递给[IMAPISession:: 注销](imapisession-logoff.md)。 传递**MAPI_LOGOFF_SHARED**将导致所有 MAPI 客户端都开始关闭, 并将发生意外行为。 
  
## <a name="see-also"></a>另请参阅



[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[结束 MAPI 会话](ending-a-mapi-session.md)

