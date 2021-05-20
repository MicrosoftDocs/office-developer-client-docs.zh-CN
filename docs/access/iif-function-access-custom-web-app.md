---
title: 'Access 自定义 web (IIf 函数) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 58a24f46-c61d-432a-a957-d831e960795d
description: 检查条件是否满足，如果为 TRUE，则返回另一个值（如果为 FALSE）。
ms.openlocfilehash: 274a923a96b58421f365b03c566a3a1c16b7c48c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439077"
---
# <a name="iif-function-access-custom-web-app"></a>Access 自定义 web (IIf 函数) 

检查条件是否满足，如果为 TRUE，则返回另一个值（如果为 FALSE）。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**IIf** (*条件*、 *TrueValue*、 *FalseValue*)  
  
**IIf** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *条件*  <br/> |要计算表达式。  <br/> |
| *TrueValue*  <br/> |如果 Condition 为 True，则  *返回值*  或表达式。  <br/> |
| *FalseValue*  <br/> |如果 Condition 为 False，则  *返回*  值或表达式。  <br/> |
   
## <a name="example"></a>示例

下面的表达式可用于显示表中包含 FirstName、MiddleInitial 和 LastName 字段的人的全名。 如果 MiddleInitial 字段为空，则只合并 FirstName 和 LastName 字段以显示全名。
  
`IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))`


