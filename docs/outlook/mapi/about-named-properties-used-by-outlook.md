---
title: 关于 Outlook 使用的命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8c245ec2-bb18-ecf0-b4ad-8c164c5924cf
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 328ff423025689795669d661f529270886123a7e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322237"
---
# <a name="about-named-properties-used-by-outlook"></a>关于 Outlook 使用的命名属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供将名称分配给某些特定属性、将这些名称映射到唯一标识符以及使这个名称到标识符的映射跨会话保持不变的工具。 命名属性由名称和属性集的全局唯一标识符 (GUID) 标识。 名称可以是数字或字符串。 对于 Microsoft Outlook 2013 或 Microsoft Outlook 2010，属性集通常是由 Outlook 2013 或 Outlook 2010 定义的命名空间，如 **PSETID_Appointment**。 
  
命名属性通过使用 [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) 函数和 [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) 函数进行操作。 将名称和属性集 GUID 传递给 [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) 函数以获取对当前 MAPI 会话有效的属性标识符。 由于此属性标识符可能因计算机而异，因此访问命名属性的唯一一致方法是知道其名称和属性集 GUID。 标识符的范围始终位于 0x8000 到 0xFFFE 之间。 
  
实现 [IMAPIProp: IUnknown](imapipropiunknown.md) 界面的任何对象可支持命名属性。 具体来说，MAPI 服务提供程序或 MAPI 客户端必须实现 [IMAPIProp::GetProps](imapiprop-getprops.md) 以获取命名属性的值。 不支持设置 Outlook 2013 或 Outlook 2010 使用的命名属性，因为存在损坏与其他 MAPI 提供程序或客户端共享的数据的风险。 
  
Outlook 2013 和 Outlook 2010 使用 MAPI 命名属性实现其许多功能，例如附件安全性和会议反建议。 在此基础数据之上，Outlook 2013 和 Outlook 2010 会公开这些属性中的某些属性作为 Outlook 2013 和 Outlook 2010 对象模型中的项属性。 例如，对象模型中 **ContactItem** 对象的 **Email1Address** 属性与 **PSETID_Address** 命名空间中的命名 [PidLidEmail1EmailAddress 规范属性](pidlidemail1emailaddress-canonical-property.md)对应。 但一般情况下，由于兼容性和数据完整性问题，Outlook 2013 和 Outlook 2010 使用的许多 MAPI 属性不会在对象模型中公开。 
  
此参考描述了下面列出的许多命名属性。
  
**PSETID_Address** 命名空间中的命名属性如下： 
  
- [PidLidEmail1AddressType 规范属性](pidlidemail1addresstype-canonical-property.md)
    
- [PidLidEmail1EmailAddress 规范属性](pidlidemail1emailaddress-canonical-property.md)
    
- [PidLidEmail1OriginalEntryId 规范属性](pidlidemail1originalentryid-canonical-property.md)
    
- [PidLidEmail2AddressType 规范属性](pidlidemail2addresstype-canonical-property.md)
    
- [PidLidEmail2DisplayName 规范属性](pidlidemail2displayname-canonical-property.md)
    
- [PidLidEmail2EmailAddress 规范属性](pidlidemail2emailaddress-canonical-property.md)
    
- [PidLidEmail2OriginalDisplayName 规范属性](pidlidemail2originaldisplayname-canonical-property.md)
    
- [PidLidEmail2OriginalEntryId 规范属性](pidlidemail2originalentryid-canonical-property.md)
    
- [PidLidEmail3AddressType 规范属性](pidlidemail3addresstype-canonical-property.md)
    
- [PidLidEmail3DisplayName 规范属性](pidlidemail3displayname-canonical-property.md)
    
- [PidLidEmail3EmailAddress 规范属性](pidlidemail3emailaddress-canonical-property.md)
    
- [PidLidEmail3OriginalDisplayName 规范属性](pidlidemail3originaldisplayname-canonical-property.md)
    
- [PidLidEmail3OriginalEntryId 规范属性](pidlidemail3originalentryid-canonical-property.md)
    
- [PidLidEmail1DisplayName 规范属性](pidlidemail1displayname-canonical-property.md)
    
- [PidLidEmail1OriginalDisplayName 规范属性](pidlidemail1originaldisplayname-canonical-property.md)
    
- [PidLidFileUnder 规范属性](pidlidfileunder-canonical-property.md)
    
- [PidLidInstantMessagingAddress 规范属性](pidlidinstantmessagingaddress-canonical-property.md)
    
- [PidLidWorkAddressCity 规范属性](pidlidworkaddresscity-canonical-property.md)
    
- [PidLidWorkAddressCountry 规范属性](pidlidworkaddresscountry-canonical-property.md)
    
- [PidLidWorkAddressPostalCode 规范属性](pidlidworkaddresspostalcode-canonical-property.md)
    
- [PidLidWorkAddressPostOfficeBox 规范属性](pidlidworkaddresspostofficebox-canonical-property.md)
    
- [PidLidWorkAddressState 规范属性](pidlidworkaddressstate-canonical-property.md)
    
- [PidLidWorkAddressStreet 规范属性](pidlidworkaddressstreet-canonical-property.md)
    
- [PidLidYomiCompanyName 规范属性](pidlidyomicompanyname-canonical-property.md)
    
- [PidLidYomiFirstName 规范属性](pidlidyomifirstname-canonical-property.md)
    
- [PidLidYomiLastName 规范属性](pidlidyomilastname-canonical-property.md)
    
**PSETID_Appointment** 命名空间中的命名属性如下： 
  
- [PidLidAllAttendeesString 规范属性](pidlidallattendeesstring-canonical-property.md)
    
- [PidLidAppointmentCounterProposal 规范属性](pidlidappointmentcounterproposal-canonical-property.md)
    
- [PidLidAppointmentDuration 规范属性](pidlidappointmentduration-canonical-property.md)
    
- [PidLidAppointmentEndWhole 规范属性](pidlidappointmentendwhole-canonical-property.md)
    
- [PidLidAppointmentStartWhole 规范属性](pidlidappointmentstartwhole-canonical-property.md)
    
- [PidLidBusyStatus 规范属性](pidlidbusystatus-canonical-property.md)
    
- [PidLidCcAttendeesString 规范属性](pidlidccattendeesstring-canonical-property.md)
    
- [PidLidLocation 规范属性](pidlidlocation-canonical-property.md)
    
- [PidLidRecurring 规范属性](pidlidrecurring-canonical-property.md)
    
- [PidLidToAttendeesString 规范属性](pidlidtoattendeesstring-canonical-property.md)
    
**PSETID_Common** 命名空间中的命名属性如下： 
  
- [PidLidCommonEnd 规范属性](pidlidcommonend-canonical-property.md)
    
- [PidLidCommonStart 规范属性](pidlidcommonstart-canonical-property.md)
    
- [PidLidCompanies 规范属性](pidlidcompanies-canonical-property.md)
    
- [PidLidContacts 规范属性](pidlidcontacts-canonical-property.md)
    
- [PidLidCustomFlag 规范属性](pidlidcustomflag-canonical-property.md)
    
- [PidLidFormPropStream 规范属性](pidlidformpropstream-canonical-property.md)
    
- [PidLidFormStorage 规范属性](pidlidformstorage-canonical-property.md)
    
- [PidLidHeaderItem 规范属性](pidlidheaderitem-canonical-property.md)
    
- [PidLidPageDirStream 规范属性](pidlidpagedirstream-canonical-property.md)
    
- [PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)
    
- [PidLidReminderSet 规范属性](pidlidreminderset-canonical-property.md)
    
- [PidLidReminderTime 规范属性](pidlidremindertime-canonical-property.md)
    
- [PidLidFlagRequest 规范属性](pidlidflagrequest-canonical-property.md)
    
- [PidLidScriptStream 规范属性](pidlidscriptstream-canonical-property.md)
    
- [PidLidSmartNoAttach 规范属性](pidlidsmartnoattach-canonical-property.md)
    
- [PidLidToDoTitle 规范属性](pidlidtodotitle-canonical-property.md)
    
- [PidLidUseTnef 规范属性](pidlidusetnef-canonical-property.md)
    
**PSETID_Meeting** 命名空间中的命名属性如下： 
  
- [PidLidMeetingType 规范属性](pidlidmeetingtype-canonical-property.md)
    
**PSETID_Task** 命名空间中的命名属性如下： 
  
- [PidLidTaskActualEffort 规范属性](pidlidtaskactualeffort-canonical-property.md)
    
- [PidLidTaskDueDate 规范属性](pidlidtaskduedate-canonical-property.md)
    
- [PidLidTaskEstimatedEffort 规范属性](pidlidtaskestimatedeffort-canonical-property.md)
    
- [PidLidTaskFRecurring 规范属性](pidlidtaskfrecurring-canonical-property.md)
    
- [PidLidTaskStartDate 规范属性](pidlidtaskstartdate-canonical-property.md)
    
- [PidLidTaskStatus 规范属性](pidlidtaskstatus-canonical-property.md)
    
**PS_INTERNET_HEADERS** 命名空间中的命名属性如下： 
  
- [PidTagInternetReturnPath 规范属性](pidtaginternetreturnpath-canonical-property.md)
    
**PSETID_Log** 命名空间中的命名属性如下： 
  
- [PidLidLogDuration 规范属性](pidlidlogduration-canonical-property.md)
    
- [PidLidLogEnd 规范属性](pidlidlogend-canonical-property.md)
    
- [PidLidLogStart 规范属性](pidlidlogstart-canonical-property.md)
    
- [PidLidLogType 规范属性](pidlidlogtype-canonical-property.md)
    
**PS_PUBLIC_STRINGS** 命名空间中的命名属性如下： 
  
- [PidNameKeywords 规范属性](pidnamekeywords-canonical-property.md)
    
- [PidNameExchangeJunkEmailMoveStamp 规范属性](pidnameexchangejunkemailmovestamp-canonical-property.md)
    
## <a name="see-also"></a>另请参阅



[MAPI 常量](mapi-constants.md)
  
[确定 Outlook 是否仅下载邮件头](how-to-determine-if-outlook-downloaded-only-the-header-of-a-message.md)
  
[获取联系人项的电子邮件地址](how-to-get-the-email-address-of-a-contact-item.md)
  
[删除随邮件一起保存的自定义表单定义](how-to-remove-custom-form-definition-saved-with-a-message.md)

