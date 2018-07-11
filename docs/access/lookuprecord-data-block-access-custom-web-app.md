---
title: LookupRecord 数据块 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 001899f7-5b1a-4c0b-a0e4-e01985eea818
description: LookupRecord 数据块可对特定记录执行一组操作。
ms.openlocfilehash: 7012fecdf0e73647b2b8177473dd8b5540b5fcca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773483"
---
# <a name="lookuprecord-data-block-access-custom-web-app"></a>LookupRecord 数据块 （访问自定义 web 应用程序）

**LookupRecord** 数据块可对特定记录执行一组操作。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
> [!NOTE]
> [!注释] **LookupRecord** 数据块仅适用于数据宏。 
  
## <a name="setting"></a>设置

**SetField** 操作具有以下参数。 
  
|**参数**|**必需**|**说明**|
|:-----|:-----|:-----|
| _In_ <br/> |可访问  <br/> |一个字符串，标识的记录执行操作。 *在*参数可以包含表、 选择查询或 SQL 语句的名称。  <br/> |
| _Where Condition_ <br/> |否  <br/> |执行字符串表达式，用来限制在其上的数据区域**LookupRecord**数据块。 例如，criteria通常是相当于 SQL 表达式中的 WHERE 子句位置，但是不使用 WHERE一词。 如果省略条件， **LookupRecord**数据块运行上指定*中*参数的整个域。 条件中包括的任何字段必须同时是*中*的字段。  <br/> |
| _Alias_ <br/> |否  <br/> |提供*在*参数指定的记录的替代名称的字符串。 通常用于缩短后续参考，以防止可能出现的不明确引用的表名称。 如果未指定*别名*，则表或查询名称将用作别名。  <br/> |
   
## <a name="remarks"></a>注释

如果  *In*  和  *Where Condition*  参数指定的条件指定了多条记录， **LookupRecord** 数据块将只对第一条记录执行操作。 
  
如果没有记录满足*Where Condition*或如果*中*不包含任何记录， **LookupRecord**将创建一个空的记录，其中的所有字段包含**Null**值。 
  

