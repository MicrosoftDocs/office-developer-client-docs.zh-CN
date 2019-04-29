---
title: PROP_ACCT_ID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b72124aa-2e85-057c-9343-a40af60b91a0
description: 返回一个标识符, 用于唯一标识在其中创建帐户的配置文件中的帐户。
ms.openlocfilehash: dcb0a7935b9b764c44088971a1acb1f3647cbdb0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407163"
---
# <a name="propacctid"></a>PROP_ACCT_ID

返回一个标识符, 用于唯一标识在其中创建帐户的配置文件中的帐户。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0001  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|属性标记：  <br/> |0x00010003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。 如果客户端尝试设置此属性, 则此属性返回**E_OLK_PROP_READ_ONLY**。 
  
此属性与[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md)的不同之处是, 它的值仅在创建帐户的配置文件中的所有帐户中是唯一的, 而属性**\_ACCT_MINI_UID**可唯一标识中的帐户和在其中创建帐户的配置文件之外。 当具有这些属性的邮件将使用不同的 Outlook 配置文件和不同的帐户集漫游到另一台计算机上时, **PROP_ACCT_ID**可能会与第二台计算机的配置文件中的帐户发生冲突, 并**PROP_ACCT_MINI_UID**可以唯一地标识原始配置文件中的原始帐户。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)

