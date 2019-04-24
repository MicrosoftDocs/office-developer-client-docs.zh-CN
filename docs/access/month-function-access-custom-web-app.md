---
title: Month 函数 (Access 自定义 web 应用)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5df43594-a434-4fb7-8109-e5cf0401ae09
description: 返回一个 integer 类型的值, 该值代表指定日期的月份。
ms.openlocfilehash: 0ca7059a2fd6dad1f9790ad6f4eafe7affa014dd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308139"
---
# <a name="month-function-access-custom-web-app"></a>Month 函数 (Access 自定义 web 应用)

返回一个 integer 类型的值, 该值代表指定日期的月份。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **月**(*Date*) 
  
**Month**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Date*  <br/> |可以解析为日期/时间值的表达式。  <br/> |
   
## <a name="remarks"></a>注解

 **month**返回与**DatePart** (月, date) 相同的值。 
  
如果*Date*仅包含一个时间部分, 则返回值为 1, 即基本月份。 
  

