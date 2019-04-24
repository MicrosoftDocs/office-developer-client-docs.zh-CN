---
title: DateAdd 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7174c585-86e1-42a3-bb7f-d6641001b0f2
description: 返回一个指定的数字间隔 (正或负整数) 添加到该日期的指定日期部分的指定日期。
ms.openlocfilehash: 7cfd68c4983eee22a5e542facd72ea083deb3184
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282178"
---
# <a name="dateadd-function-access-custom-web-app"></a>DateAdd 函数 (Access 自定义 web 应用程序)

返回一个指定的数字间隔 (正或负整数) 添加到该日期的指定日期部分的指定日期。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateAdd**(*DatePart*、 *Number*、 *Date*) 
  
**DateAdd**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *DatePart*  <br/> |要向其中添加整数的*日期*部分。 有关有效设置的列表, 请参阅 "备注" 部分。  <br/> |
| *Number*  <br/> |是一个表达式, 可解析为一个整数, 该整数将添加到日期的*日期**部分*。 如果指定十进制小数的值, 则分数将被截尾取整。  <br/> |
| *Date*  <br/> |可以解析为日期/时间值的表达式。 *日期*参数表达式、列表达式、用户定义的变量或字符串文本。  <br/> |
   
## <a name="remarks"></a>注解

下表列出了所有有效的*DatePart*参数。 
  
|***DatePart***|
|:-----|
|**year** <br/> |
|**结算** <br/> |
|**month** <br/> |
|**dayofyear** <br/> |
|**为期** <br/> |
|**周** <br/> |
|**七点** <br/> |
|**还要** <br/> |
|**第二个** <br/> |
|**加** <br/> |
   
## <a name="example"></a>示例

下面的表达式计算当月的最后一天。
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today())+1,0))`

下面的表达式计算上个月的最后一天。
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today()),0))`


