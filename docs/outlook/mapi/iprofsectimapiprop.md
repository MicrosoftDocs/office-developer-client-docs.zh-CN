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
ms.openlocfilehash: 99ce944bec94a1e832f77fa8b0916ac1c76f6dc6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406596"
---
# <a name="iprofsect--imapiprop"></a>IProfSect : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
适用于 profile 节对象的属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix  <br/> |
|公开者:  <br/> |Profile 部分对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
|接口标识符:  <br/> |IID_IProfSect  <br/> |
|指针类型:  <br/> |LPPROFSECT  <br/> |
|事务模型:  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

此接口没有任何唯一的方法。
  
|**必需属性**|**访问**|
|:-----|:-----|
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_PROFILE_NAME**([PidTagProfileName](pidtagprofilename-canonical-property.md))  <br/> |只读  <br/> |
   
## <a name="notes-to-callers"></a>给调用方的说明

**IProfSect**接口没有自己的任何唯一方法, 但您可以调用 profile 节的[IMAPIProp](imapipropiunknown.md)方法。 在**IProfSect**实现和**IMAPIProp**的其他实现之间存在一些差异:
  
- **IProfSect**不支持事务模型。 
    
- **IProfSect**不支持命名属性。 
    
- **IProfSect**保留用于安全属性的标识符范围0x67F0 到0x67ff。 
    
不支持事务模型意味着在调用[IMAPIProp:: CopyProps](imapiprop-copyprops.md)和[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法后, 对配置文件节所做的所有更改都将立即发生。 对[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法的调用会成功, 但实际上并不会保存任何更改。 
  
为了防止发生过早发生的更改, 服务提供商需要通过属性表向用户显示其配置文件节的副本。 属性表应适用于副本, 而不是实际的配置文件部分。 当用户单击 **"确定"** 按钮以验证更改是否正确时, 可以将更改保存到 "实际配置文件" 部分。 
  
若要使用已复制的 profile 节实现属性表, 请使用以下过程:
  
1. 通过调用[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)或[IProviderAdmin:: OpenProfileSection](iprovideradmin-openprofilesection.md)方法打开 "配置文件" 部分。 
    
2. 调用[CreateIProp](createiprop.md)函数以检索属性数据对象, 即支持**IPropData**接口的对象。 
    
3. 调用 profile 节的[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法将属性表上显示的属性从配置文件部分复制到属性数据对象。 
    
4. 调用[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法, 以请求服务提供程序显示属性表, 并在_lpConfigData_参数中传递指向属性数据对象的指针。 
    
5. 当用户在属性表中保存对配置属性所做的更改时, 调用[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法将属性数据对象中的属性复制回 "配置文件" 部分。 
    
与其他对象不同, 配置文件节不支持命名属性。 如果在 profile 节对象上调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)方法, 则将返回 MAPI_E_NO_SUPPORT。 如果使用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法在0x8000 上方的范围中设置属性标识符, 则将返回 PT_ERROR 属性类型。 
  
配置文件节为安全属性保留0x67F0 到0x67FF 的标识符范围。 服务提供程序可以使用此范围来存储密码和其他特定于提供程序的凭据。 如果在[IMAPIProp:: GetProps](imapiprop-getprops.md)方法的_lpPropTag_参数中传递 NULL 时, 不会在属性的完整列表中返回此范围中的属性, 也不会在该范围的_lppPropTagArray_参数[中返回这些属性。IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法。 安全属性必须由其标识符专门请求。 
  
MAPI 提供使用硬编码常量 MUID_PROFILE_INSTANCE 作为其单个属性的标识符和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 作为配置文件节。 MAPI 可确保所有创建的配置文件中的**PR_SEARCH_KEY**属性值都是唯一的。 如果唯一性非常重要, 则使用**PR_SEARCH_KEY**而不是**PR_PROFILE_NAME** , 因为可能会有一个已删除的配置文件后跟另一个具有相同名称的配置文件。 
  
有关如何使用配置文件节的详细信息, 请参阅[管理配置文件和邮件服务](administering-profiles-and-message-services.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

