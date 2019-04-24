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
ms.openlocfilehash: de0c1181450c536dffd5a84242c17bd1dd612566
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270096"
---
# <a name="mapiopenformmgr"></a>MAPIOpenFormMgr

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在现有会话的上下文中打开表单库提供程序对象上的[IMAPIFormMgr](imapiformmgriunknown.md)接口。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
MAPIOpenFormMgr(
  LPMAPISESSION pSession,
  LPMAPIFORMMGR FAR * ppmgr
);
```

## <a name="parameters"></a>参数

 _pSession_
  
> 实时指向客户端应用程序正在使用的会话的指针。
    
 _ppmgr_
  
> 排除指向返回的**IMAPIFormMgr**接口的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

在客户端应用程序调用**MAPIOpenFormMgr**函数之后, 大多数随后与表单相关的交互通过表单库提供程序或由表单库提供程序返回的接口进行。 **IMAPIFormMgr**接口允许客户端处理邮件处理程序, 并在邮件类别和表单库之间执行解析。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg 打开窗体管理器, 以便可以选择窗体。  <br/> |CMainDlg:: OnSelectForm  <br/> |MFCMAPI 使用**MAPIOpenFormMgr**方法打开表单管理器, 以便可以选择表单。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

