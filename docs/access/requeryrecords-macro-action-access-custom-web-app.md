---
title: RequeryRecords 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1dab102f-24af-4984-8020-a9fb06355639
description: 您可以使用 RequeryRecords 操作刷新、 排序和筛选通过重新查询视图的源的活动视图中的数据。
ms.openlocfilehash: 27c6a4f62f62f6d903de7a23d2aca6db8d316a84
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773593"
---
# <a name="requeryrecords-macro-action-access-custom-web-app"></a>RequeryRecords 宏操作 （访问自定义 web 应用程序）

您可以使用**RequeryRecords**操作刷新、 排序和筛选通过重新查询视图的源的活动视图中的数据。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**RequeryRecords**操作具有下列参数。 
  
|**参数**|**必需**|**说明**|
|:-----|:-----|:-----|
|**其中 =** <br/> |否  <br/> |一个 SQL WHERE 子句限制视图中的记录。 默认情况下，此参数为空。  <br/> |
|**OrderBy** <br/> |否  <br/> |一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。 默认情况下，此参数为空。  <br/> |
   
## <a name="remarks"></a>说明

调用**RequeryRecords**操作时，会清除任何排序或筛选用户应用的。 
  
*OrderBy*参数是在您要对记录进行排序的字段的名称。 如果使用多个字段名称，需用逗号 (,) 分隔每个名称。 
  
当设置*OrderBy*参数时，记录将默认情况下按升序排序。 
  
若要按降序顺序记录排序，输入 DESC *OrderBy*参数表达式的末尾。 例如，若要客户记录联系人姓名按降序排序，设置"ContactName DESC"的*OrderBy*参数。 
  
若要排序的降序的 LastName 和 FirstName 升序的名称，请将*OrderBy*参数设置为"LastName DESC，FirstName ASC"。 
  

