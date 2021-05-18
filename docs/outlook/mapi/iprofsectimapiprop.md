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
  
使用配置文件节对象的属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix.h  <br/> |
|公开者：  <br/> |配置文件节对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
|接口标识符：  <br/> |IID_IProfSect  <br/> |
|指针类型：  <br/> |LPPROFSECT  <br/> |
|事务模型：  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

此接口没有任何唯一的方法。
  
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |只读  <br/> |
|**PR_PROFILE_NAME (** [PidTagProfileName](pidtagprofilename-canonical-property.md))   <br/> |只读  <br/> |
   
## <a name="notes-to-callers"></a>给调用方的说明

**IProfSect** 接口没有其自己的任何唯一方法，但您可以调用配置文件节的 [IMAPIProp](imapipropiunknown.md)方法。 **IProfSect** 实现与 **IMAPIProp** 的其他实现之间存在一些差异：
  
- **IProfSect** 不支持事务模型。 
    
- **IProfSect** 不支持命名属性。 
    
- **IProfSect** 保留标识符0x67F0 0x67ff安全属性。 
    
不支持事务模型意味着调用 [IMAPIProp：：CopyProps](imapiprop-copyprops.md) 和 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法后对配置文件节进行的所有更改会立即发生。 对 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法的调用成功，但实际上并未保存任何更改。 
  
若要防止提前更改，服务提供商需要复制其配置文件部分，这些部分通过属性表显示给用户。 属性表应处理副本，而不是实际配置文件部分。 当用户单击" **确定"** 按钮以验证更改是否准确时，可以将更改保存到真实的配置文件部分。 
  
若要使用属性表配置文件部分实现一个配置文件，请使用以下过程：
  
1. 通过调用 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 或 [IProviderAdmin：：OpenProfileSection](iprovideradmin-openprofilesection.md) 方法打开配置文件部分。 
    
2. 调用 [CreateIProp](createiprop.md) 函数以检索属性数据对象（支持 **IPropData 接口** 的对象）。 
    
3. 调用配置文件节的 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法，将出现在配置文件属性表上的属性复制到属性数据对象。 
    
4. 调用 [IMAPISupport：:D oConfigPropSheet](imapisupport-doconfigpropsheet.md) 方法以请求服务提供商显示 属性表，并传递指向  _lpConfigData_ 参数中的属性数据对象的指针。 
    
5. 当用户在配置文件中保存对配置属性属性表，请调用 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法将属性从属性数据对象复制回配置文件部分。 
    
配置文件节与其他对象不同，不支持命名属性。 如果对配置文件节对象调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 和 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 方法MAPI_E_NO_SUPPORT将返回值。 如果使用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法设置上述 0x8000 范围中的属性标识符，PT_ERROR返回属性类型。 
  
配置文件部分保留标识符范围0x67F0 0x67FF安全属性。 服务提供商可以使用此范围来存储密码和其他提供程序特定的凭据。 [在 IMAPIProp：：GetProps](imapiprop-getprops.md)方法的 _lpPropTag_ 参数中传递 NULL 时，不会在属性的完整列表中返回此范围中的属性，也不会在 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)方法的 _lppPropTagArray_ 参数中返回这些属性。 安全属性必须由其标识符专门请求。 
  
MAPI 为配置文件节提供硬编码常量 MUID_PROFILE_INSTANCE 作为其标识符，PR_SEARCH_KEY ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 用作其单个属性。  MAPI 确保PR_SEARCH_KEY **属性值在所有** 创建的配置文件中是唯一的。 如果 **PR_SEARCH_KEY** 唯 **一** PR_PROFILE_NAME，请使用"文件"，而不是"文件"，因为已删除的配置文件后面可以跟有同名的另一个配置文件。 
  
有关如何使用配置文件部分的信息，请参阅 [管理配置文件和邮件服务](administering-profiles-and-message-services.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

