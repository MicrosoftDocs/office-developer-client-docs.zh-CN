---
title: ForEachRecord 数据块 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8ffa0de2-5abb-4375-9fb5-042ce3c21506
description: ForEachRecord 数据块的域中的每个记录都重复一组语句。
ms.openlocfilehash: 8ad14a01be05de9fb34299e49a9737f2009ef5ef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773459"
---
# <a name="foreachrecord-data-block-access-custom-web-app"></a>ForEachRecord 数据块 （访问自定义 web 应用程序）

**ForEachRecord**数据块的域中的每个记录都重复一组语句。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> [!注释] **ForEachRecord** 数据块仅适用于数据宏。 
  
## <a name="setting"></a>设置

**ForEachRecord** 操作具有以下参数。 
  
|**参数名称**|**必需**|**说明**|
|:-----|:-----|:-----|
|**In** <br/> |可访问  <br/> |一个字符串，标识的记录执行操作的域。 *在*参数可以包含表、 选择查询或 SQL 语句的名称。  <br/> **注意**： 指定的域不能包括链接的表或 ODBC 数据源中存储的数据。           |
|**Where Condition** <br/> |否  <br/> |执行字符串表达式，用来限制在其上的数据区域**ForEachRecord**数据块。 例如，criteria通常是相当于 SQL 表达式中的 WHERE 子句位置，但是不使用 WHERE一词。 如果条件都被忽略， **ForEachRecord**数据块运行上指定*中*参数的整个域。 条件中包括的任何字段必须同时是*中*的字段。  <br/> |
|**Alias** <br/> |否  <br/> |提供*在*参数指定的域的替代名称的字符串。 通常用于缩短后续参考，以防止可能出现的不明确引用的表名称。 如果未指定*别名*，则表或查询名称将用作别名。  <br/> |
   
## <a name="remarks"></a>注释

使用 **[ExitForEachRecord](exitforeachrecord-macro-action-access-custom-web-app.md)** 操作可立即退出 **ForEachRecord** 数据块。 
  

