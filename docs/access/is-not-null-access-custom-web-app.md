---
title: IS [NOT] NULL（Access 自定义 Web 应用）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
ms.assetid: b941a0c7-9753-4920-bb6d-cbba94ba9422
description: 确定指定的表达式是否为 NULL。
localization_priority: Priority
ms.openlocfilehash: fe6a0fe4f182a1385304b783e7cfaaf515f732d4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311135"
---
# <a name="is-not-null-access-custom-web-app"></a>IS [NOT] NULL（Access 自定义 Web 应用）

确定指定的表达式是否为 NULL。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *expression* **IS** [  *NOT*  ] **NULL**
  
**IS [NOT] NULL** 谓词包含以下参数。 
  
|||
|:-----|:-----|
| *expression*  <br/> |任何有效的表达式。  <br/> |
| *NOT*  <br/> |指定布尔结果取反。 该谓词将对其返回值取反，如果值为非 NULL，则返回 TRUE，如果值为 NULL，则返回 FALSE。  <br/> |
   
## <a name="remarks"></a>备注

如果 *expression* 的值为 NULL，则 IS NULL 返回 TRUE；否则返回 FALSE。 
  
如果 expression 的值为 NULL，则 IS NULL 返回 TRUE；否则返回 FALSE。
  

