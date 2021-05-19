---
title: IMsgServiceAdminGetMsgServiceTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.GetMsgServiceTable
api_type:
- COM
ms.assetid: 064dd5ca-0108-4045-b17b-0bb29cb93346
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fcaebb96d4dca4e6bfbee7491dabeafcbd93a2eb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410474"
---
# <a name="imsgserviceadmingetmsgservicetable"></a>IMsgServiceAdmin::GetMsgServiceTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对邮件服务表（配置文件中邮件服务的列表）的访问权限。
  
```cpp
HRESULT GetMsgServiceTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]始终为 NULL。
    
 _lppTable_
  
> [out]指向指向邮件服务表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回邮件服务表。
    
## <a name="remarks"></a>备注

**IMsgServiceAdmin：：GetMsgServiceTable** 方法提供对邮件服务表的访问，该表是 MAPI 维护的一个表，其中列出了会话配置文件中当前安装的邮件服务。 有关邮件服务表中列的完整列表，请参阅 [Message Service Table](message-service-tables.md)。
  
邮件服务表是静态的。 在客户端获得访问权后，后续邮件服务添加或删除操作将不会影响客户端。 如果当前配置文件中没有任何邮件服务 **，GetMsgServiceTable** 将返回一个包含零行的表。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgServiceTableDlg.cpp  <br/> |CMsgServiceTableDlg：：OnRefreshView  <br/> |MFCMAPI 使用 **IMsgServiceAdmin：：GetMsgServiceTable** 方法在配置文件中加载要呈现在视图中的服务表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[IMsgServiceAdmin::DeleteMsgService](imsgserviceadmin-deletemsgservice.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

