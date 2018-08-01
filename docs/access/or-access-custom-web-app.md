---
title: 或者 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7190523-87cf-4e04-aef4-d229776cd16b
description: 结合以下两种情况。 当任一两个条件为 true，则返回 TRUE。
ms.openlocfilehash: 8ccf4a12644f45e80756f72013d42310fece07fd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773576"
---
# <a name="or-access-custom-web-app"></a>或者 （访问自定义 web 应用程序）

结合以下两种情况。 当任一两个条件为 true，则返回 TRUE。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *布尔表达式***或***布尔表达式* 
  
**Or**运算符使用以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *布尔表达式*  <br/> |返回 TRUE 或 FALSE 任何有效表达式。  <br/> |
   
## <a name="remarks"></a>说明

在语句中使用多个逻辑运算符时，**或**运算符计算后**和**运算符。 但是，您可以通过使用括号更改求值的顺序。 
  
下表显示了**Or**运算符的结果。 
  
||**TRUE**|**FALSE**|
|:-----|:-----|:-----|
|**TRUE** <br/> |TRUE  <br/> |TRUE  <br/> |
|**FALSE** <br/> |TRUE  <br/> |FALSE  <br/> |
   

