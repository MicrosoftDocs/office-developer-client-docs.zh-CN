---
title: IOlkEnum
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 33cb89cb-c967-760c-6bc4-94118a4f872c
ms.openlocfilehash: be91a56f93b787f5570139768d96eb4f7fe9ac02
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774372"
---
# <a name="iolkenum"></a>IOlkEnum

支持枚举作为[IUnknown](http://msdn.microsoft.com/library/com.iunknown%28Office.15%29.aspx)对象的帐户。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|通过实现：  <br/> |Outlook  <br/> |
|提供者：  <br/> |[IOlkAccountManager::EnumerateAccounts](iolkaccountmanager-enumerateaccounts.md) <br/> |
|调用：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IOlkEnum  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[GetCount](iolkenum-getcount.md) <br/> |获取枚举中的帐户数。  <br/> |
|[Reset](iolkenum-reset.md) <br/> |重将枚举器重置到开头。  <br/> |
|[GetNext](iolkenum-getnext.md) <br/> |获取枚举中的下一个帐户。  <br/> |
|[跳过](iolkenum-skip.md) <br/> |跳过指定的数量的枚举中的帐户。  <br/> |
   
## <a name="remarks"></a>说明

此接口返回**IOlkAccountManager::EnumerateAccounts**时获取帐户的枚举。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

