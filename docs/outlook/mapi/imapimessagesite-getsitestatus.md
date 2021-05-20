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
  
> [out]指向标志的位掩码的指针，该标记提供有关邮件状态的信息。 可以设置以下标志：
    
VCSTATUS_COPY 
  
> 可以复制邮件。 
    
VCSTATUS_DELETE 
  
> 可以删除该邮件。
    
VCSTATUS_DELETE_IS_MOVE 
  
> 删除邮件时，邮件将移动到其邮件存储中的"已删除邮件"文件夹，而不是立即从邮件存储中删除。 
    
VCSTATUS_MOVE 
  
> 可以移动邮件。
    
VCSTATUS_NEW_MESSAGE 
  
> 可以新建邮件。
    
VCSTATUS_SAVE 
  
> 可以保存邮件。
    
VCSTATUS_SUBMIT 
  
> 可以提交邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

Form 对象调用 **IMAPIMessageSite：：GetSiteStatus** 方法以获取邮件网站对象对当前邮件的功能。 _lpulStatus_ 参数中返回的标志提供有关邮件站点的信息。 通常，窗体启用或禁用菜单命令，具体取决于标志提供的有关邮件网站实现功能的信息。 如果 [IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) 方法或 [IPersistMessage：：Load](ipersistmessage-load.md) 方法将新邮件加载到表单中，则必须检查状态标志。 某些邮件网站对象（尤其是只读对象）不允许保存或删除邮件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

**IMAPIMessageSite：：GetSiteStatus** 方法可能要求客户端应用程序执行一些计算，以确定可以或不能对当前消息执行的操作。 通常，这涉及到查看当前邮件的邮件存储提供程序的状态行，或查询存储提供程序以确定客户端应用程序可以使用邮件存储执行的操作。 例如，若要确定是否返回 MAPI_DELETE_IS_MOVE 标志，请检查邮件存储对象的 **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 属性以查看邮件存储中是否有"已删除邮件"文件夹。  
  
有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：GetSiteStatus  <br/> |MFCMAPI 使用 **IMAPIMessageSite：：GetSiteStatus** 方法获取指定站点的状态。 它可以返回VCSTATUS_NEW_MESSAGE、VCSTATUS_SAVE或VCSTATUS_SUBMIT。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IPersistMessage::Load](ipersistmessage-load.md)
  
[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)
  
[PidTagIpmWastebasketEntryId 规范属性](pidtagipmwastebasketentryid-canonical-property.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

