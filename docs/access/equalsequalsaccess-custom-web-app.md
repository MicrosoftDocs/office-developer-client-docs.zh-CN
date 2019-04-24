---
title: Equals (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 70bc707a-3a61-4d75-816d-0defd0806319
description: 比较两个表达式的相等性。
ms.openlocfilehash: 8c551e3dbc057433b49bc2558e08feba5ee3d04f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308223"
---
# <a name="equals-access-custom-web-app"></a>Equals (Access 自定义 web 应用程序)

比较两个表达式的相等性。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

`= (Equals)`

*表达式*  =  *表达式* 
  
“*expression*”表示任何有效的表达式。 如果表达式不是相同的数据类型, 则一个表达式的数据类型必须可以隐式转换为另一个表达式的数据类型。 转换取决于数据类型优先级的规则。 
  
## <a name="return-type"></a>返回类型

**Boolean**
  
## <a name="remarks"></a>备注

比较两个 NULL 表达式时, 结果为 TRUE。
  
将 NULL 与非 NULL 值进行比较始终会导致 FALSE。
  

