---
title: LookupRecord 数据块 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 001899f7-5b1a-4c0b-a0e4-e01985eea818
description: LookupRecord 数据块可对特定记录执行一组操作。
ms.openlocfilehash: a6d89b1700a47f88086fd8c4e7b594b90425912c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434359"
---
# <a name="lookuprecord-data-block-access-custom-web-app"></a>LookupRecord 数据块 (Access 自定义 web 应用程序)

**LookupRecord** 数据块可对特定记录执行一组操作。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> **LookupRecord** 数据块仅适用于数据宏。 
  
## <a name="setting"></a>Setting

**SetField** 操作具有以下参数。 
  
|**参数**|**必需**|**描述**|
|:-----|:-----|:-----|
| _实时_ <br/> |是  <br/> |一个用于标识要对其执行操作的记录的字符串。 *In*参数可以包含表、选择查询或 SQL 语句的名称。  <br/> |
| _Where 条件_ <br/> |否  <br/> |一个字符串表达式，用于限制对其执行 **LookupRecord** 数据块的数据的范围。 例如，条件通常相当于 SQL 表达式中的 WHERE 子句（无单词 WHERE）。 如果省略条件, 则**LookupRecord**数据块在由*In*参数指定的整个域上运行。 条件中包含的任何字段都必须也是中的字段** 。  <br/> |
| _Alias_ <br/> |否  <br/> |为*In*参数所指定的记录提供可选名称的字符串。 通常用于缩短后续引用的表名称，以防止可能出现的不明引用。 如果未指定*alias* , 则表或查询名称将用作别名。  <br/> |
   
## <a name="remarks"></a>说明

如果  *In*  和  *Where Condition*  参数指定的条件指定了多条记录， **LookupRecord** 数据块将只对第一条记录执行操作。 
  
如果没有记录满足*Where 条件*或*In*不包含记录, 则**LookupRecord**将创建一个空白记录, 其中所有字段都包含一个**Null**值。 
  

