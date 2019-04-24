---
title: DateFromParts 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4fa49d5f-12ea-4d14-9a03-28418f01746c
description: 返回指定的年、月和日的日期值。
ms.openlocfilehash: 7d47fe93d1990365f1db5885a3ea8fc056aabb9f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282120"
---
# <a name="datefromparts-function-access-custom-web-app"></a>DateFromParts 函数 (Access 自定义 web 应用程序)

返回指定的年、月和日的日期值。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateFromParts**(*年*、*月*、*日*) 
  
**DateFromParts**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Year*  <br/> |指定一年的整数表达式。  <br/> |
| *Month*  <br/> |指定1到12之间的月份的整数表达式。  <br/> |
| *Day*  <br/> |指定一天的整数表达式。  <br/> |
   
## <a name="remarks"></a>注解

**DateFromParts**返回日期部分设置为指定的年、月和日以及将时间部分设置为默认值的 date 值。 如果参数无效, 则会引发错误。 如果必需的参数为 null, 则返回 null。 
  
## <a name="example"></a>示例

下面的表达式使用**DateFromParts**函数计算当月的第一天。 
  
`DateFromParts(Year(Today()),Month(Today()),1)`



