---
title: '等于 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 70bc707a-3a61-4d75-816d-0defd0806319
description: 比较两个表达式的等同性。
ms.openlocfilehash: 8c551e3dbc057433b49bc2558e08feba5ee3d04f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408927"
---
# <a name="equals-access-custom-web-app"></a>等于 (Access 自定义 Web 应用) 

比较两个表达式的等同性。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

`= (Equals)`

*表达式*   =  *表达式* 
  
“*expression*”表示任何有效的表达式。 如果表达式与另一个表达式数据类型，数据类型表达式的表达式必须隐式转换为另数据类型的表达式。 转换取决于数据类型优先级的规则。 
  
## <a name="return-type"></a>返回类型

**Boolean**
  
## <a name="remarks"></a>说明

比较两个 NULL 表达式时，结果为 TRUE。
  
将 NULL 与非 NULL 值进行比较始终会导致 FALSE。
  

