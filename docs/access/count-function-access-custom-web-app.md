---
title: Count 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: d931535b-428f-4300-93bf-cfe0ebcc2ac9
description: 返回查询或表中的记录数。
ms.openlocfilehash: 300fcbfd2aa927dd19516355ae28eec2adadf521
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773458"
---
# <a name="count-function-access-custom-web-app"></a>Count 函数 （访问自定义 web 应用程序）

返回查询或表中的记录数。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**计数**（*表达式*） 
  
**Count**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Expression*  <br/> |标识了包含数据的字段的字符串表达式要计数或表达式的计算使用字段中的数据。 *表达式*中的操作数可以包括表字段或函数 （这可能是固有或用户定义但不是其他 SQL 聚合函数） 的名称。 可以计算包括文本在内的任何类型数据。  <br/> |
   
## <a name="remarks"></a>说明

可以使用 Count 来统计基本查询的记录数。 例如，可以使用 Count 来计算发往的特定国家或地区的订单数。
  
**计数**(\*) 返回组中的项目数。 这包括 NULL 值和重复项。 
  

