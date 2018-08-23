---
title: IProfSect IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfSect
api_type:
- COM
ms.assetid: 4e704044-5230-4521-a0d2-b7c2f981c954
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8152a9cad7623a077cd9df3f678a9ada56e3960
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577959"
---
# <a name="iprofsect--imapiprop"></a>IProfSect : IMAPIProp

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
适用于配置文件部分对象的属性。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapix.h  <br/> |
|由公开：  <br/> |配置文件部分对象  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
|接口标识符：  <br/> |IID_IProfSect  <br/> |
|指针类型：  <br/> |LPPROFSECT  <br/> |
|事务模型：  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

此接口不具有任何唯一的方法。
  
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_PROFILE_NAME**([PidTagProfileName](pidtagprofilename-canonical-property.md))  <br/> |只读  <br/> |
   
## <a name="notes-to-callers"></a>给调用方的说明

**IProfSect**接口不具有其自己的任何唯一方法，但是您可以调用该配置文件节的[IMAPIProp](imapipropiunknown.md)方法。 有一些**IProfSect**实施和**IMAPIProp**其他实现之间的区别：
  
- **IProfSect**不支持事务模型。 
    
- **IProfSect**不支持命名的属性。 
    
- **IProfSect**保留标识符的范围 0x67F0 到 0x67ff 安全属性。 
    
不支持事务模型意味着，所做的所有更改配置文件部分以下都呼叫到[IMAPIProp::CopyProps](imapiprop-copyprops.md)和[IMAPIProp::CopyTo](imapiprop-copyto.md)方法立即发生。 调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法成功，但实际不保存任何更改。 
  
若要防止提前发生的更改，服务提供商需要进行的属性表通过向用户显示其配置文件部分副本。 属性表应使用的副本，而不是实际的配置文件部分。 当用户单击**确定**按钮以验证所做的更改准确时，实际的配置文件一节可以保存所做的更改。 
  
若要通过使用复制的配置文件部分实现属性表，请使用以下过程：
  
1. 通过调用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)或[IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md)方法打开配置文件部分。 
    
2. 调用[CreateIProp](createiprop.md)函数以检索属性数据对象 — 支持**IPropData**接口的对象。 
    
3. 调用复制属性将出现在从配置文件部分对属性的数据对象的属性表上的配置文件部分的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法。 
    
4. 调用[IMAPISupport::DoConfigPropSheet](imapisupport-doconfigpropsheet.md)方法可以请求服务提供商显示属性表，并将指针传递给_lpConfigData_参数中的属性数据对象。 
    
5. 当用户将更改保存到属性表中的配置属性时，调用[IMAPIProp::CopyTo](imapiprop-copyto.md)方法以返回到配置文件部分，从属性数据对象复制属性。 
    
配置文件节，与其他对象不同，不支持命名的属性。 如果在配置文件部分对象上调用它们， [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)方法的返回 MAPI_E_NO_SUPPORT。 如果您使用[IMAPIProp::SetProps](imapiprop-setprops.md)方法上方 0x8000 范围中设置属性标识符，将返回 PT_ERROR 属性类型。 
  
配置文件部分保留标识符的范围 0x67F0 到 0x67FF 安全属性。 服务提供商可以使用此范围可存储密码和其他特定于提供程序的凭据。 [IMAPIProp::GetProps](imapiprop-getprops.md)方法的_lpPropTag_参数中传递空值和它们以[的_lppPropTagArray_参数返回时，此范围中的属性不返回中属性的完整列表IMAPIProp::GetPropList](imapiprop-getproplist.md)方法。 安全属性必须专门通过其标识符来请求。 
  
MAPI 作为其单个属性与作为其标识符的硬编码常量 MUID_PROFILE_INSTANCE **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 提供配置文件一节。 MAPI 确保**PR_SEARCH_KEY**属性值将是唯一的而创建的所有配置文件。 唯一性很重要，因为这样跟具有相同名称的另一个配置文件的已删除配置文件时，请使用**PR_SEARCH_KEY**而不是**PR_PROFILE_NAME** 。 
  
有关如何使用配置文件节，请参阅[管理配置文件和消息服务](administering-profiles-and-message-services.md)的详细信息。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

