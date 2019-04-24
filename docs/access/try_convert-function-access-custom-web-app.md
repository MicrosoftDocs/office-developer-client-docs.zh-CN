---
title: Try_Convert 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea514f19-4742-4eb4-823d-6f2494668106
description: 将值转换为指定的数据类型, 如果转换无效, 则返回 Null。
ms.openlocfilehash: 473d9063da46652afa88dc974cb4c4036e1c326c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304223"
---
# <a name="tryconvert-function-access-custom-web-app"></a>Try_Convert 函数 (Access 自定义 web 应用程序)

将值转换为指定的数据类型, 如果转换无效, 则返回 Null。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Try_Convert**(*DataType*、 *Expression*) 
  
**Try_Convert**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *DataType*  <br/> |要将*表达式*转换为的数据类型。  <br/> |
| *Expression*  <br/> |要转换的值。  <br/> |
   
## <a name="remarks"></a>注解

 **Try_Convert**获取传递给它的值, 并尝试将其转换为指定的*数据类型*。 如果转换成功, **Try_Convert**将以指定的*数据类型*返回值;如果发生错误, 则返回 null。 但是, 如果您请求显式不允许的转换, 则**Try_Convert**将失败并出现错误。 
  

