---
title: 关于附加 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 78e2806d-bb6f-cd96-21f1-b7c667c73c33
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fefa77a15cc2b8c72a41b29e6299f159a893cee8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322160"
---
# <a name="about-mapi-additions"></a>关于附加 MAPI

**适用于**：Outlook 2013 | Outlook 2016 
  
mapi 添加项是属于邮件应用程序编程接口 (MAPI) 的 api, 这些接口 (如数据类型、函数和属性) 之前未作为 MAPI 程序员参考的一部分公开和记录。 其中包括以下定义和属性。
  
## <a name="constant-definitions"></a>常量定义

- **[其他 MAPI 常量](mapi-constants.md)**
  
## <a name="data-types"></a>数据类型

- **[EXCHANGE_STORE_VERSION_NUM](exchange_store_version_num.md)**
    
- **[FollowUpStatus](followupstatus.md)**
    
- **[Gender](gender.md)**
    
- **[OlFlagIcon](olflagicon.md)**
    
## <a name="functions"></a>函数

- **[FixMAPI](fixmapi.md)**
    
## <a name="properties"></a>属性

以下属性通常由 message 对象公开。
  
- **[PR_BODY_W](pidtagbody-canonical-property.md)**
    
- **[PR_CONFLICT_ITEMS](pidtagconflictitems-canonical-property.md)**
    
- **[PR_DISPLAY_BCC_W](pidtagdisplaybcc-canonical-property.md)**
    
- **[PR_DISPLAY_CC_W](pidtagdisplaycc-canonical-property.md)**
    
- **[PR_DISPLAY_TO_W](pidtagdisplayto-canonical-property.md)**
    
- **[PR_FLAG_STATUS](pidtagflagstatus-canonical-property.md)**
    
- **[PR_FOLLOWUP_ICON](pidtagfollowupicon-canonical-property.md)**
    
- **[PR_INETMAIL_OVERRIDE_FORMAT](pidtaginternetmailoverrideformat-canonical-property.md)**
    
- **[PR_MESSAGE_CLASS_W](pidtagmessageclass-canonical-property.md)**
    
- **[PR_MSG_EDITOR_FORMAT](pidtagmessageeditorformat-canonical-property.md)**
    
- **[PR_NORMALIZED_SUBJECT_W](pidtagnormalizedsubject-canonical-property.md)**
    
- **[PR_SENDER_ADDRTYPE_W](pidtagsenderaddresstype-canonical-property.md)**
    
- **[PR_SENDER_EMAIL_ADDRESS_W](pidtagsenderemailaddress-canonical-property.md)**
    
- **[PR_SENDER_NAME_W](pidtagsendername-canonical-property.md)**
    
- **[PR_SENT_REPRESENTING_ADDRTYPE_W](pidtagsentrepresentingaddresstype-canonical-property.md)**
    
- **[PR_SENT_REPRESENTING_EMAIL_ADDRESS_W](pidtagsentrepresentingemailaddress-canonical-property.md)**
    
- **[PR_SENT_REPRESENTING_NAME_W](pidtagsentrepresentingname-canonical-property.md)**
    
- **[PR_SUBJECT_PREFIX_W](pidtagsubjectprefix-canonical-property.md)**
    
- **[PR_SUBJECT_W](pidtagsubject-canonical-property.md)**
    
下列属性由通讯簿内容表对象公开。
  
- **[PR_DISPLAY_TYPE_EX](pidtagdisplaytypeex-canonical-property.md)**
    
下列属性由通讯簿容器对象公开。
  
- **[PR_EMS_AB_SERVER](pidtagemsabserver-canonical-property.md)**
    
- **[PR_EMS_AB_SERVER_A](pidtagemsabserver-canonical-property.md)**
    
- **[PR_EMS_AB_SERVER_W](pidtagemsabserver-canonical-property.md)**
    
下列属性由 folder 对象公开。
  
- **[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)**
    
- **[PR_AGING_PERIOD](pidtagagingperiod-canonical-property.md)**
    
以下属性由邮件用户对象公开。
  
- **[PR_ASSISTANT_TELEPHONE_NUMBER_W](pidtagassistanttelephonenumber-canonical-property.md)**
    
- **[PR_ASSISTANT_W](pidtagassistant-canonical-property.md)**
    
- **[PR_ATTACHMENT_CONTACTPHOTO](pidtagattachmentcontactphoto-canonical-property.md)**
    
- **[PR_BIRTHDAY](pidtagbirthday-canonical-property.md)**
    
- **[PR_BUSINESS_FAX_NUMBER_W](pidtagbusinessfaxnumber-canonical-property.md)**
    
- **[PR_BUSINESS_HOME_PAGE_W](pidtagbusinesshomepage-canonical-property.md)**
    
- **[PR_CALLBACK_TELEPHONE_NUMBER_W](pidtagcallbacktelephonenumber-canonical-property.md)**
    
- **[PR_CAR_TELEPHONE_NUMBER_W](pidtagcartelephonenumber-canonical-property.md)**
    
- **[PR_CELLULAR_TELEPHONE_NUMBER_W](pidtagmobiletelephonenumber-canonical-property.md)**
    
- **[PR_CHILDRENS_NAMES_W](pidtagchildrensnames-canonical-property.md)**
    
- **[PR_DEPARTMENT_NAME_W](pidtagdepartmentname-canonical-property.md)**
    
- **[PR_DISPLAY_NAME_PREFIX_W](pidtagdisplaynameprefix-canonical-property.md)**
    
- **[PR_GENDER](pidtaggender-canonical-property.md)**
    
- **[PR_GENERATION_W](pidtaggeneration-canonical-property.md)**
    
- **[PR_GIVEN_NAME_W](pidtaggivenname-canonical-property.md)**
    
- **[PR_HOBBIES_W](pidtaghobbies-canonical-property.md)**
    
- **[PR_HOME_ADDRESS_CITY_W](pidtaghomeaddresscity-canonical-property.md)**
    
- **[PR_HOME_ADDRESS_COUNTRY_W](pidtaghomeaddresscountry-canonical-property.md)**
    
- **[PR_HOME_ADDRESS_POST_OFFICE_BOX_W](pidtaghomeaddresspostofficebox-canonical-property.md)**
    
- **[PR_HOME_ADDRESS_POSTAL_CODE_W](pidtaghomeaddresspostalcode-canonical-property.md)**
    
- **[PR_HOME_ADDRESS_STATE_OR_PROVINCE_W](pidtaghomeaddressstateorprovince-canonical-property.md)**
    
- **[PR_HOME_ADDRESS_STREET_W](pidtaghomeaddressstreet-canonical-property.md)**
    
- **[PR_HOME_FAX_NUMBER_W](pidtaghomefaxnumber-canonical-property.md)**
    
- **[PR_HOME_TELEPHONE_NUMBER_W](pidtaghometelephonenumber-canonical-property.md)**
    
- **[PR_KEYWORD_W](pidtagkeyword-canonical-property.md)**
    
- **[PR_MANAGER_NAME_W](pidtagmanagername-canonical-property.md)**
    
- **[PR_MIDDLE_NAME_W](pidtagmiddlename-canonical-property.md)**
    
- **[PR_NICKNAME_W](pidtagnickname-canonical-property.md)**
    
- **[PR_OFFICE_LOCATION_W](pidtagofficelocation-canonical-property.md)**
    
- **[PR_OFFICE_TELEPHONE_NUMBER_W](pidtagbusinesstelephonenumber-canonical-property.md)**
    
- **[PR_OTHER_ADDRESS_CITY_W](pidtagotheraddresscity-canonical-property.md)**
    
- **[PR_OTHER_ADDRESS_COUNTRY_W](pidtagotheraddresscountry-canonical-property.md)**
    
- **[PR_OTHER_ADDRESS_POST_OFFICE_BOX_W](pidtagotheraddresspostofficebox-canonical-property.md)**
    
- **[PR_OTHER_ADDRESS_POSTAL_CODE_W](pidtagotheraddresspostalcode-canonical-property.md)**
    
- **[PR_OTHER_ADDRESS_STATE_OR_PROVINCE_W](pidtagotheraddressstateorprovince-canonical-property.md)**
    
- **[PR_OTHER_ADDRESS_STREET_W](pidtagotheraddressstreet-canonical-property.md)**
    
- **[PR_PAGER_TELEPHONE_NUMBER_W](pidtagpagertelephonenumber-canonical-property.md)**
    
- **[PR_PERSONAL_HOME_PAGE_W](pidtagpersonalhomepage-canonical-property.md)**
    
- **[PR_PRIMARY_TELEPHONE_NUMBER_W](pidtagprimarytelephonenumber-canonical-property.md)**
    
- **[PR_PROFESSION_W](pidtagprofession-canonical-property.md)**
    
- **[PR_SPOUSE_NAME_W](pidtagspousename-canonical-property.md)**
    
- **[PR_SURNAME_W](pidtagsurname-canonical-property.md)**
    
- **[PR_TITLE_W](pidtagtitle-canonical-property.md)**
    
- **[PR_TTYTDD_PHONE_NUMBER_W](pidtagttytddphonenumber-canonical-property.md)**
    
- **[PR_WEDDING_ANNIVERSARY](pidtagweddinganniversary-canonical-property.md)**
    
以下属性由 profile 节对象公开。
  
- **[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)**
    
- **[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)**
    
- **[PR_PROVIDER_DISPLAY_NAME_W](pidtagproviderdisplayname-canonical-property.md)**
    
- **[PR_PROVIDER_ICON_W](pidtagprovidericon-canonical-property.md)**
    
- **[PR_ROH_FLAGS](pidtagrpcoverhttpflags-canonical-property.md)**
    
- **[PR_ROH_PROXY_AUTH_SCHEME](pidtagrpcoverhttpproxyauthscheme-canonical-property.md)**
    
- **[PR_ROH_PROXY_PRINCIPAL_NAME](pidtagrpcoverhttpproxyprincipalname-canonical-property.md)**
    
- **[PR_ROH_PROXY_SERVER](pidtagrpcoverhttpproxyserver-canonical-property.md)**
    
以下属性由存储对象公开。
  
- **[PR_IPM_APPOINTMENT_ENTRYID](pidtagipmappointmententryid-canonical-property.md)**
    
- **[PR_IPM_CONTACT_ENTRYID](pidtagipmcontactentryid-canonical-property.md)**
    
- **[PR_IPM_DRAFTS_ENTRYID](pidtagipmdraftsentryid-canonical-property.md)**
    
- **[PR_IPM_JOURNAL_ENTRYID](pidtagipmjournalentryid-canonical-property.md)**
    
- **[PR_IPM_NOTE_ENTRYID](pidtagipmnoteentryid-canonical-property.md)**
    
- **[PR_IPM_TASK_ENTRYID](pidtagipmtaskentryid-canonical-property.md)**
    
以下属性由存储对象公开, 并在存储中搜索电子邮件的特定元素时使用。
  
- **[PR_SEARCH_ATTACHMENTS_W](pidtagsearchattachments-canonical-property.md)**
    
- **[PR_SEARCH_RECIP_EMAIL_BCC_W](pidtagsearchrecipientemailbcc-canonical-property.md)**
    
- **[PR_SEARCH_RECIP_EMAIL_CC_W](pidtagsearchrecipientemailcc-canonical-property.md)**
    
- **[PR_SEARCH_RECIP_EMAIL_TO_W](pidtagsearchrecipientemailto-canonical-property.md)**
    
## <a name="see-also"></a>另请参阅

- [当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)  
- [在 Outlook 配置文件中检测 Exchange Server 的版本](how-to-detect-the-version-of-exchange-server-in-an-outlook-profile.md)
- [当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)
- [在缓存 Exchange 模式下管理 OST 中的邮件（不调用同步）](how-to-manage-a-message-in-an-ost-without-invoking-a-synchronization.md)

