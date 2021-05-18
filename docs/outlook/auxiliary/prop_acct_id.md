---
title: PROP_ACCT_ID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b72124aa-2e85-057c-9343-a40af60b91a0
description: 返回一个唯一标识创建帐户的配置文件中的帐户的标识符。
ms.openlocfilehash: dcb0a7935b9b764c44088971a1acb1f3647cbdb0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407163"
---
# <a name="prop_acct_id"></a>PROP_ACCT_ID

返回一个唯一标识创建帐户的配置文件中的帐户的标识符。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0001  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|属性标记：  <br/> |0x00010003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>备注

使用 [IOlkAccount：：GetProp 获取此属性](iolkaccount-getprop.md)。 如果客户端尝试设置此属性，则此属性返回 E_OLK_PROP_READ_ONLY **。** 
  
此属性不同于 [PROP_ACCT_MINI_UID，](prop_acct_mini_uid.md) 因为其值仅在创建帐户的配置文件内的所有帐户之间是唯一的，而 **PROP \_ ACCT_MINI_UID** 用于唯一标识创建帐户的配置文件内外的帐户。 当具有这些属性的邮件漫游到具有不同 Outlook 配置文件和一组不同帐户的第二台计算机时 **，PROP_ACCT_ID** 可能会与第二台计算机的配置文件中的帐户发生冲突，**并且 PROP_ACCT_MINI_UID** 可以唯一地标识原始配置文件中的原始帐户。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)

