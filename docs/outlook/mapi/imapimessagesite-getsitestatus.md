---
title: IMAPIMessageSiteGetSiteStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetSiteStatus
api_type:
- COM
ms.assetid: 02718898-7857-4e43-8f46-622269f812e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7d81533b13f4f44a0644215e009dc3477717e9a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775461"
---
# <a name="imapimessagesitegetsitestatus"></a>IMAPIMessageSite::GetSiteStatus

  
  
**适用于**： Outlook 
  
返回信息有关邮件消息网站对象中为当前消息的网站的功能。
  
```cpp
HRESULT GetSiteStatus(
  ULONG FAR * lpulStatus
);
```

## <a name="parameters"></a>参数

 _lpulStatus_
  
> [输出]一个指向提供有关邮件状态信息的标志位掩码。 可以设置以下标志：
    
VCSTATUS_COPY 
  
> 可以复制邮件。 
    
VCSTATUS_DELETE 
  
> 可以删除邮件。
    
VCSTATUS_DELETE_IS_MOVE 
  
> 删除时，邮件移动到而不是从其消息存储库立即删除其消息存储库中的**已删除邮件**文件夹。 
    
VCSTATUS_MOVE 
  
> 邮件可被移动。
    
VCSTATUS_NEW_MESSAGE 
  
> 可以创建一个新的邮件。
    
VCSTATUS_SAVE 
  
> 可以保存该邮件。
    
VCSTATUS_SUBMIT 
  
> 可以提交邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

表单对象调用**IMAPIMessageSite::GetSiteStatus**方法获取当前消息的消息网站对象的功能。 _LpulStatus_参数中返回的标志提供有关邮件网站的信息。 通常情况下，窗体启用或禁用菜单命令，具体取决于标志提供有关功能的信息的邮件网站实现。 如果新邮件[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)方法或[IPersistMessage::Load](ipersistmessage-load.md)方法加载到窗体时，必须检查状态标志。 某些消息网站对象，尤其是只读的对象，不允许保存或删除的邮件。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

**IMAPIMessageSite::GetSiteStatus**方法可能需要进行一些计算，以确定操作可以或不能对当前邮件执行客户端应用程序。 通常情况下，涉及的当前消息的消息存储提供程序，看的状态行或查询的存储提供程序，以确定哪些操作的客户端应用程序可以执行使用的消息存储。 例如，若要确定是否返回 MAPI_DELETE_IS_MOVE 标志，检查消息存储对象**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 属性以查看是否存在中的**已删除邮件**文件夹邮件存储区。 
  
有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::GetSiteStatus  <br/> |MFCMAPI 使用**IMAPIMessageSite::GetSiteStatus**方法获取指定网站的状态。 它可以返回 VCSTATUS_NEW_MESSAGE、 VCSTATUS_SAVE 或 VCSTATUS_SUBMIT。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IPersistMessage::Load](ipersistmessage-load.md)
  
[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)
  
[PidTagIpmWastebasketEntryId 规范属性](pidtagipmwastebasketentryid-canonical-property.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

