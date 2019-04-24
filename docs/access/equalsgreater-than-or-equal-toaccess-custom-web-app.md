---
title: 大于或等于（Access 自定义 Web 应用）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
ms.assetid: cceb8dcb-5ce1-4c32-b057-6201b62a646f
description: 比较两个大于或等于的表达式。
localization_priority: Priority
ms.openlocfilehash: 76472544be950c68f3b5d42fe13b3040e9268f48
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302497"
---
# <a name="greater-than-or-equal-to-access-custom-web-app"></a>大于或等于（Access 自定义 Web 应用）

比较两个大于或等于的表达式。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

`>= (Greater Than or Equal To)`

*expression*  \>=  *expression* 
  
*expression* 表示任何有效的表达式。 两个表达式必须具有隐式可转换的数据类型。 转换取决于数据类型优先级的规则。 
  
## <a name="return-type"></a>返回类型

**Boolean**
  
## <a name="remarks"></a>备注

比较非 Null 表达式时，如果左操作数大于或等于右操作数，结果为 TRUE；否则结果为 FALSE。
  

