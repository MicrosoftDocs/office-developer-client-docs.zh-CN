---
title: IIf 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 58a24f46-c61d-432a-a957-d831e960795d
description: 检查它是否条件得到满足，并在如果如果为 true，则另一个返回一个值为 FALSE。
ms.openlocfilehash: 26240735341a316a3aed08a12c42e8b6e7af805f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773425"
---
# <a name="iif-function-access-custom-web-app"></a>IIf 函数 （访问自定义 web 应用程序）

检查它是否条件得到满足，并在如果如果为 true，则另一个返回一个值为 FALSE。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

**IIf**(*条件*， *TrueValue*， *FalseValue*) 
  
**IIf**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *条件*  <br/> |要计算的表达式。  <br/> |
| *TrueValue*  <br/> |值或表达式返回如果*条件*为 True。  <br/> |
| *FalseValue*  <br/> |值或表达式返回如果*条件*为 False。  <br/> |
   
## <a name="example"></a>示例

以下表达式可显示联系人的完整名称其中表包含 FirstName、 MiddleInitial 和 LastName 字段。 如果 MiddleInitial 字段为空，组合仅的 FirstName 和 LastName 字段以显示完整的名称。
  
`IIf([MiddleInitial] Is Null,Concat([FirstName]," ",[LastName]),Concat([FirstName]," ",[MiddleInitial]," ",[LastName]))`


