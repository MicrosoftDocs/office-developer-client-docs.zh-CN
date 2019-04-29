---
title: IIf 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 58a24f46-c61d-432a-a957-d831e960795d
description: 检查是否满足某个条件, 如果另一个条件为 FALSE, 则返回一个值。
ms.openlocfilehash: 274a923a96b58421f365b03c566a3a1c16b7c48c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439077"
---
# <a name="iif-function-access-custom-web-app"></a>IIf 函数 (Access 自定义 web 应用程序)

检查是否满足某个条件, 如果另一个条件为 FALSE, 则返回一个值。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**IIf**(*Condition*、 *TrueValue*、 *FalseValue*) 
  
**IIf**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *条件*  <br/> |要计算的表达式。  <br/> |
| *TrueValue*  <br/> |如果*条件*为 True, 则返回值或表达式。  <br/> |
| *FalseValue*  <br/> |如果*Condition*为 False, 则返回值或表达式。  <br/> |
   
## <a name="example"></a>示例

下面的表达式可用于显示表中包含 FirstName、MiddleInitial 和 LastName 字段的人员的完整名称。 如果 "MiddleInitial" 字段为空, 则只会组合 "名字" 和 "姓氏" 字段以显示完整名称。
  
`IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))`


