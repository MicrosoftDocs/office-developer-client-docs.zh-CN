---
title: 等于 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 70bc707a-3a61-4d75-816d-0defd0806319
description: 比较两个表达式相等。
ms.openlocfilehash: efdd06a1735190d63c13c4df8230e1d29d71c1dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773462"
---
# <a name="equals-access-custom-web-app"></a>等于 （访问自定义 web 应用程序）

比较两个表达式相等。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

`= (Equals)`

*表达式*  =  *表达式* 
  
*表达式* 是任何有效的表达式。 如果表达式不属于同一字段数据类型，必须隐式转换为的数据类型的另一个表达式的数据类型。 转换取决于数据类型优先级的规则。 
  
## <a name="return-type"></a>返回类型

**Boolean**
  
## <a name="remarks"></a>说明

当您比较两个 NULL 表达式时，则结果为 TRUE。
  
始终为非 NULL 值比较 NULL 导致 FALSE。
  

