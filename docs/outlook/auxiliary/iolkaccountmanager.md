---
title: IOlkAccountManager
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 544c87e5-887d-82ec-bf1a-0d95027fe0ec
ms.openlocfilehash: 5657aeb5f710281a1dcb482b3ebf15049e085b11
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413652"
---
# <a name="iolkaccountmanager"></a>IOlkAccountManager

管理对帐户的访问权限并设置有关帐户更改的通知。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自：  <br/> |[IOlkErrorUnknown](iolkerrorunknown.md) <br/> |
|实现者：  <br/> |Outlook  <br/> |
|提供者：  <br/> |CLSID_OlkAccountManager  <br/> |
|调用者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IOlkAccountManager  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[初始](iolkaccountmanager-init.md) <br/> |初始化帐户管理器以使用。  <br/> |
|[DisplayAccountList](iolkaccountmanager-displayaccountlist.md) <br/> |Displays either the **Account 设置** or Add **New Account** dialog box.  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
|[FindAccount](iolkaccountmanager-findaccount.md) <br/> |按属性值查找帐户。  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
|[DeleteAccount](iolkaccountmanager-deleteaccount.md) <br/> |删除指定的帐户。  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
|[SaveChanges](iolkaccountmanager-savechanges.md) <br/> |保存对指定帐户的更改。  <br/> |
|[GetOrder](iolkaccountmanager-getorder.md) <br/> |获取指定帐户类别的排序。  <br/> |
|[SetOrder](iolkaccountmanager-setorder.md) <br/> |修改指定帐户类别的排序。  <br/> |
|[EnumerateAccounts](iolkaccountmanager-enumerateaccounts.md) <br/> |获取特定类别和类型的帐户的枚举器。  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
|[FreeMemory](iolkaccountmanager-freememory.md) <br/> |释放由 **IOlkAccountManager** 接口分配的内存。  <br/> |
|[建议](iolkaccountmanager-advise.md) <br/> |向帐户管理员注册客户端，以接收有关所有帐户的通知。  <br/> |
|[非企业](iolkaccountmanager-unadvise.md) <br/> |使用帐户管理器注销客户端，以通知所有帐户。  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
| *占位符成员*  <br/> | *不支持或记录*  <br/> |
   
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)

