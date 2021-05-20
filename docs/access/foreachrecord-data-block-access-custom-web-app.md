---
title: 'ForEachRecord Data Block (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8ffa0de2-5abb-4375-9fb5-042ce3c21506
description: ForEachRecord 数据块对域中每条记录重复一组语句。
ms.openlocfilehash: 9715824bff7d478fa2880ada5e8770f7a0c88883
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428233"
---
# <a name="foreachrecord-data-block-access-custom-web-app"></a>ForEachRecord Data Block (Access 自定义 Web 应用) 

**ForEachRecord** 数据块对域中每条记录重复一组语句。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> **ForEachRecord** 数据块仅适用于数据宏。 
  
## <a name="setting"></a>设置

**ForEachRecord** 操作具有以下参数。 
  
|**参数名称**|**必需**|**描述**|
|:-----|:-----|:-----|
|**In** <br/> |是  <br/> |一个用于标识要对其执行操作的记录域的字符串。 *In* 参数可以包含表的名称、选择查询或 SQL 语句。  <br/> **注意**：指定域不能包括链接表或 ODBC 数据源中存储的数据。           |
|**Where 条件** <br/> |否  <br/> |字符串表达式，用于限制作为 **ForEachRecord** 数据块执行对象的数据的范围。 例如，条件通常相当于 SQL 表达式中的 WHERE 子句（无单词 WHERE）。 如果省略 **criteria，ForEachRecord** 数据块将运行在  *In*  参数指定的整个域上。 任何包含在 criteria 中的字段也必须是 In 中的  *字段*  。  <br/> |
|**Alias** <br/> |否  <br/> |为 In 参数指定的域提供备用名称 *的字符串。* 通常用于缩短后续引用的表名称，以防止可能出现的不明引用。 如果  *未指定 Alias，*  表或查询名称将用作别名。  <br/> |
   
## <a name="remarks"></a>备注

使用 **[ExitForEachRecord](exitforeachrecord-macro-action-access-custom-web-app.md)** 操作可立即退出 **ForEachRecord** 数据块。 
  

