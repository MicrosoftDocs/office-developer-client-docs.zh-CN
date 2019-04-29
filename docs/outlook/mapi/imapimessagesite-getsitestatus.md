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
ms.openlocfilehash: ab4a06a20c71943f9b649d8f22377f59223e9717
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430124"
---
# <a name="imapimessagesitegetsitestatus"></a>IMAPIMessageSite::GetSiteStatus

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从邮件网站对象返回有关当前邮件的邮件网站功能的信息。
  
```cpp
HRESULT GetSiteStatus(
  ULONG FAR * lpulStatus
);
```

## <a name="parameters"></a>参数

 _lpulStatus_
  
> 排除指向提供有关邮件状态的信息的标志的位掩码的指针。 可以设置以下标志:
    
VCSTATUS_COPY 
  
> 可以复制邮件。 
    
VCSTATUS_DELETE 
  
> 可以删除邮件。
    
VCSTATUS_DELETE_IS_MOVE 
  
> 删除后, 邮件将移到其邮件存储区中的 "**已删除**邮件" 文件夹中, 而不是立即从邮件存储库中删除。 
    
VCSTATUS_MOVE 
  
> 可以移动邮件。
    
VCSTATUS_NEW_MESSAGE 
  
> 可以创建新邮件。
    
VCSTATUS_SAVE 
  
> 可以保存邮件。
    
VCSTATUS_SUBMIT 
  
> 可以提交邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

表单对象调用**IMAPIMessageSite:: GetSiteStatus**方法来获取当前邮件的邮件网站对象的功能。 _lpulStatus_参数中返回的标志提供有关邮件网站的信息。 通常情况下, 窗体启用或禁用菜单命令, 具体取决于标志提供的有关邮件网站实现功能的信息。 如果通过[IPersistMessage:: SaveCompleted](ipersistmessage-savecompleted.md)方法或[IPersistMessage:: Load](ipersistmessage-load.md)方法将新邮件加载到表单中, 则必须选中状态标志。 某些邮件网站对象 (尤其是只读对象) 不允许保存或删除邮件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

**IMAPIMessageSite:: GetSiteStatus**方法可能需要客户端应用程序执行某些计算, 以确定可以或无法对当前邮件执行的操作。 通常, 这涉及查看当前邮件的邮件存储提供程序的状态行, 或查询存储提供程序, 以确定客户端应用程序可以使用邮件存储执行的操作。 例如, 若要确定是否返回 MAPI_DELETE_IS_MOVE 标志, 请检查邮件存储对象的**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 属性, 以查看是否有 "**已删除邮件**" 文件夹在邮件存储区。 
  
有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer  <br/> |CMyMAPIFormViewer:: GetSiteStatus  <br/> |MFCMAPI 使用**IMAPIMessageSite:: GetSiteStatus**方法获取指定网站的状态。 它可以返回 VCSTATUS_NEW_MESSAGE、VCSTATUS_SAVE 或 VCSTATUS_SUBMIT。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IPersistMessage::Load](ipersistmessage-load.md)
  
[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)
  
[PidTagIpmWastebasketEntryId 规范属性](pidtagipmwastebasketentryid-canonical-property.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

