---
title: MAPIOpenFormMgr
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIOpenFormMgr
api_type:
- COM
ms.assetid: 5b624954-d975-4d5e-84d7-74e096ac30af
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2ed71b5eef0c25a78d7c8ec695a756a02e796dbf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586030"
---
# <a name="mapiopenformmgr"></a>MAPIOpenFormMgr

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
现有会话的上下文中打开窗体库提供程序对象上的[IMAPIFormMgr](imapiformmgriunknown.md)接口。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
MAPIOpenFormMgr(
  LPMAPISESSION pSession,
  LPMAPIFORMMGR FAR * ppmgr
);
```

## <a name="parameters"></a>参数

 _pSession_
  
> [in]加入会话，使用客户端应用程序的指针。
    
 _ppmgr_
  
> [输出]对返回**IMAPIFormMgr**接口的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

客户端应用程序，可以对**MAPIOpenFormMgr**函数的调用之后，大多数后续窗体相关进行交互通过表单库提供程序或表单库提供程序返回的接口。 **IMAPIFormMgr**界面允许客户端使用消息处理程序，并执行邮件类和窗体库之间的分辨率。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp 打开窗体管理器，以便可以选择窗体。  <br/> |CMainDlg::OnSelectForm  <br/> |MFCMAPI 使用**MAPIOpenFormMgr**方法打开窗体管理器，因此可以选择窗体。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

