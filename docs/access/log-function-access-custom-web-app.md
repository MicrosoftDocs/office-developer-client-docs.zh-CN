---
title: Log 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a897e812-08dc-49c9-954b-e8908a0daab3
description: 返回指定表达式的自然对数或给定底数的对数。
ms.openlocfilehash: e2cfd1cf4ad3c1bf44778737faa0f697333f5234
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311086"
---
# <a name="log-function-access-custom-web-app"></a>Log 函数 (Access 自定义 web 应用程序)

返回指定表达式的自然对数或给定底数的对数。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **日志**(*NumericExpression* , [ *Base* ]) 
  
**Log**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *NumericExpression*  <br/> |要对其进行对数的正数。  <br/> |
| *Base*  <br/> |对数的底数。 如果省略, 则**Log**函数返回自然对数。  <br/> |
   
## <a name="remarks"></a>注解

函数**Log10**是类似的, 但总是返回常用对数, 即底数为10的对数。 
  
自然对数是底数 e 的对数, 其中 e 是一个 irrational 常量, 约等于2.718281828。
  

