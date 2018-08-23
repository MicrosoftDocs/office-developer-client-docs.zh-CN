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
ms.openlocfilehash: 5d8e91490cc39c3f259d35a923bb3bcbb2bf6011
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568166"
---
# <a name="imsgserviceadmingetmsgservicetable"></a>IMsgServiceAdmin::GetMsgServiceTable

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
提供对邮件服务表，该配置文件中的消息服务的列表的访问。
  
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
  
> [输出]指向邮件服务表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回邮件服务表。
    
## <a name="remarks"></a>注解

**IMsgServiceAdmin::GetMsgServiceTable**方法提供对邮件服务表，一个表，MAPI 维护列出当前在会话配置中安装的消息服务的访问。 邮件服务表中的列的完整列表，请参阅[邮件服务表](message-service-tables.md)。
  
邮件服务表是静态的。 客户端具有已向其授予访问后，后续消息服务添加或删除操作不会影响它。 如果当前配置文件中没有邮件服务， **GetMsgServiceTable**返回具有零个行的表。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MsgServiceTableDlg.cpp  <br/> |CMsgServiceTableDlg::OnRefreshView  <br/> |MFCMAPI 使用**IMsgServiceAdmin::GetMsgServiceTable**方法加载配置文件以呈现在视图中的服务的表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[IMsgServiceAdmin::DeleteMsgService](imsgserviceadmin-deletemsgservice.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

