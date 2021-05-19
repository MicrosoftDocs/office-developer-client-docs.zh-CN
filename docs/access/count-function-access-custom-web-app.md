---
title: 'Access 自定义 (应用的 Count 函数) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: d931535b-428f-4300-93bf-cfe0ebcc2ac9
description: 返回查询或表中的记录数。
ms.openlocfilehash: 98dbed393bf2f6dc401119f6c5dc7ab6b5ff7864
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419140"
---
# <a name="count-function-access-custom-web-app"></a>Access 自定义 (应用的 Count 函数) 

返回查询或表中的记录数。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**计算** (*表达式*)  
  
**Count** 函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Expression*  <br/> |字符串表达式（标识包含要计算的数据的字段）或表达式（使用字段中的数据执行计算）。 Expression 中的操作数可以包括表字段或函数 (可以是固有函数或用户定义的函数，但不能包含其他SQL函数) 。 可以计算包括文本在内的任何类型数据。  <br/> |
   
## <a name="remarks"></a>备注

可以使用 Count 来统计基本查询的记录数。 例如，您可以使用 Count 计算发往特定国家/地区或地区的订单数。
  
**Count** (\*) 返回组中项的数量。 这包括 NULL 值和重复项。 
  

