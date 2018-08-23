---
title: 关于 Outlook 使用的命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8c245ec2-bb18-ecf0-b4ad-8c164c5924cf
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: aa4d52d25f120e8b3e2a4c0dcaa4845ad576127a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566227"
---
# <a name="about-named-properties-used-by-outlook"></a>关于 Outlook 使用的命名属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 提供的工具，将名称分配给特定属性、 将这些名称映射到唯一标识符，以及使此名称为标识符映射各个会话持久性。 命名的属性标识的名称和属性集的全局唯一标识符 (GUID)。 名称可以是数字或字符串。 对于 Microsoft Outlook 2013 或 Microsoft Outlook 2010，属性设置通常由 Outlook 2013 或 Outlook 2010 中，如**PSETID_Appointment**定义的命名空间。 
  
通过使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)函数和[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)函数操作时命名的属性。 名称和属性集 GUID 传递到[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)函数获取当前的 MAPI 会话是有效的属性标识符。 因为此属性标识符可以不同计算机到计算机，仅一致的方式访问的命名的属性是知道其名称和属性集 GUID。 始终位于 0x8000 和 0xFFFE 区域标识符的范围。 
  
实现任何对象[IMAPIProp: IUnknown](imapipropiunknown.md)接口可支持命名的属性。 具体而言，MAPI 服务提供商或 MAPI 客户端必须实现[IMAPIProp::GetProps](imapiprop-getprops.md)获取的命名属性的值。 名为 Outlook 2013 或 Outlook 2010 中使用的属性的设置不支持由于破坏其他 MAPI 提供程序或客户端与共享的数据的风险。 
  
Outlook 2013 和 Outlook 2010 使用 MAPI 命名属性，以实现多个及其功能，例如、 附件安全性和会议反建议。 上面这些基础数据，Outlook 2013 和 Outlook 2010 公开这些属性的一些作为其 Outlook 2013 和 Outlook 2010 对象模型中的项目属性。 例如，对象模型中的**ContactItem**对象的**Email1Address**属性对应于**PSETID_Address**命名空间中的命名[PidLidEmail1EmailAddress 规范属性](pidlidemail1emailaddress-canonical-property.md)。 但一般情况下，由于兼容性和数据完整性的问题，许多使用 Outlook 2013 和 Outlook 2010 MAPI 属性中未公开的对象模型。 
  
此参考介绍数下面列出的命名属性。
  
**PSETID_Address**命名空间中的命名的属性如下所示： 
  
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
    
**PSETID_Appointment**命名空间中的命名的属性如下所示： 
  
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
    
**PSETID_Common**命名空间中的命名的属性如下所示： 
  
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
    
**PSETID_Meeting**命名空间中的命名的属性如下所示： 
  
- [PidLidMeetingType 规范属性](pidlidmeetingtype-canonical-property.md)
    
**PSETID_Task**命名空间中的命名的属性如下所示： 
  
- [PidLidTaskActualEffort 规范属性](pidlidtaskactualeffort-canonical-property.md)
    
- [PidLidTaskDueDate 规范属性](pidlidtaskduedate-canonical-property.md)
    
- [PidLidTaskEstimatedEffort 规范属性](pidlidtaskestimatedeffort-canonical-property.md)
    
- [PidLidTaskFRecurring 规范属性](pidlidtaskfrecurring-canonical-property.md)
    
- [PidLidTaskStartDate 规范属性](pidlidtaskstartdate-canonical-property.md)
    
- [PidLidTaskStatus 规范属性](pidlidtaskstatus-canonical-property.md)
    
**PS_INTERNET_HEADERS**命名空间中的命名的属性如下所示： 
  
- [PidTagInternetReturnPath 规范属性](pidtaginternetreturnpath-canonical-property.md)
    
**PSETID_Log**命名空间中的命名的属性如下所示： 
  
- [PidLidLogDuration 规范属性](pidlidlogduration-canonical-property.md)
    
- [PidLidLogEnd 规范属性](pidlidlogend-canonical-property.md)
    
- [PidLidLogStart 规范属性](pidlidlogstart-canonical-property.md)
    
- [PidLidLogType 规范属性](pidlidlogtype-canonical-property.md)
    
**PS_PUBLIC_STRINGS**命名空间中的命名的属性如下所示： 
  
- [PidNameKeywords 规范属性](pidnamekeywords-canonical-property.md)
    
- [PidNameExchangeJunkEmailMoveStamp 规范属性](pidnameexchangejunkemailmovestamp-canonical-property.md)
    
## <a name="see-also"></a>另请参阅



[MAPI 常量](mapi-constants.md)
  
[确定 Outlook 是否仅下载邮件头](how-to-determine-if-outlook-downloaded-only-the-header-of-a-message.md)
  
[获取联系人项的电子邮件地址](how-to-get-the-email-address-of-a-contact-item.md)
  
[删除随邮件保存的自定义表单定义](how-to-remove-custom-form-definition-saved-with-a-message.md)

