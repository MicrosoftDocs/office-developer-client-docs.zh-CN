---
title: ForEachRecord 数据块 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8ffa0de2-5abb-4375-9fb5-042ce3c21506
description: ForEachRecord 数据块为域中的每条记录重复一组语句。
ms.openlocfilehash: 9715824bff7d478fa2880ada5e8770f7a0c88883
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302455"
---
# <a name="foreachrecord-data-block-access-custom-web-app"></a>ForEachRecord 数据块 (Access 自定义 web 应用程序)

**ForEachRecord**数据块为域中的每条记录重复一组语句。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> **ForEachRecord** 数据块仅适用于数据宏。 
  
## <a name="setting"></a>Setting

**ForEachRecord** 操作具有以下参数。 
  
|**参数名称**|**必需**|**描述**|
|:-----|:-----|:-----|
|**实时** <br/> |是  <br/> |一个用于标识要对其执行操作的记录域的字符串。 *In*参数可以包含表、选择查询或 SQL 语句的名称。  <br/> **注意**: 指定的域不能包含存储在链接表或 ODBC 数据源中的数据。           |
|**Where 条件** <br/> |否  <br/> |一个字符串表达式, 用于限制要对其执行**ForEachRecord**数据块的数据的范围。 例如，条件通常相当于 SQL 表达式中的 WHERE 子句（无单词 WHERE）。 如果省略条件, 则**ForEachRecord**数据块在由*In*参数指定的整个域上运行。 条件中包含的任何字段都必须也是中的字段** 。  <br/> |
|**Alias** <br/> |否  <br/> |为*In*参数指定的域提供备用名称的字符串。 通常用于缩短后续引用的表名称，以防止可能出现的不明引用。 如果未指定*alias* , 则表或查询名称将用作别名。  <br/> |
   
## <a name="remarks"></a>注解

使用 **[ExitForEachRecord](exitforeachrecord-macro-action-access-custom-web-app.md)** 操作可立即退出 **ForEachRecord** 数据块。 
  

