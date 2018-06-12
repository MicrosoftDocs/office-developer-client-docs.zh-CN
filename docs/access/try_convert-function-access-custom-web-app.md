---
title: Try_Convert 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea514f19-4742-4eb4-823d-6f2494668106
description: 将值转换为指定的数据类型，则返回 null 值，如果转换无效。
ms.openlocfilehash: ce942c1f444da7bfcbff76077a5a9d75dd611336
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773641"
---
# <a name="tryconvert-function-access-custom-web-app"></a>Try_Convert 函数 （访问自定义 web 应用程序）

将值转换为指定的数据类型，则返回 null 值，如果转换无效。
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Try_Convert**(*数据类型*，*表达式*) 
  
**Try_Convert**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *数据类型*  <br/> |到要将*表达式*转换为的数据类型。  <br/> |
| *Expression*  <br/> |要转换的值。  <br/> |
   
## <a name="remarks"></a>备注

 **Try_Convert**采用传递给它的值，并尝试将其转换为指定的*数据类型*。 如果转换成功，则**Try_Convert**返回值为指定*数据类型*;如果出现错误，则返回 null。 但是如果请求明确不允许的转换，然后**Try_Convert**失败并出现错误。 
  

