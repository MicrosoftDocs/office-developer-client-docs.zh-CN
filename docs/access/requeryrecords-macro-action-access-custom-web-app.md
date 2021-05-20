---
title: 'RequeryRecords Access 自定义 Web (宏操作) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1dab102f-24af-4984-8020-a9fb06355639
description: 可以使用 RequeryRecords 操作通过重新查询视图的源来刷新、排序和筛选活动视图中的数据。
ms.openlocfilehash: 69d88401abc0de417f7dc58e275c66f2037212aa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439245"
---
# <a name="requeryrecords-macro-action-access-custom-web-app"></a>RequeryRecords Access 自定义 Web (宏操作) 

可以使用 **RequeryRecords** 操作通过重新查询视图的源来刷新、排序和筛选活动视图中的数据。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**RequeryRecords** 操作具有下列参数。 
  
|**参数**|**必需**|**描述**|
|:-----|:-----|:-----|
|**Where=** <br/> |否  <br/> |一SQL限制视图中的记录的 WHERE 子句。 默认情况下，此参数为空。  <br/> |
|**OrderBy** <br/> |否  <br/> |一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。 默认情况下，此参数为空。  <br/> |
   
## <a name="remarks"></a>备注

调用 **RequeryRecords** 操作时，将清除用户应用的任何排序或筛选。 
  
*OrderBy* 参数是您希望对记录进行排序的一个或多个字段的名称。 如果使用多个字段名称，需用逗号 (,) 分隔每个名称。 
  
设置  *OrderBy 参数*  时，默认情况下记录按升序排序。 
  
若要按降序对记录进行排序，请在  *OrderBy*  参数表达式的末尾输入 DESC。 例如，若要按联系人姓名的降序排列客户记录，将  *OrderBy*  参数设置为"ContactName DESC"。 
  
若要按 LastName 降序和 FirstName 升序对名称进行排序，将  *OrderBy*  参数设置为"LastName DESC， FirstName ASC"。 
  

