---
title: 'DateAdd 函数 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7174c585-86e1-42a3-bb7f-d6641001b0f2
description: 返回具有指定数字间隔的指定 (正整数或负整数) 添加到该日期的指定日期部分。
ms.openlocfilehash: 7cfd68c4983eee22a5e542facd72ea083deb3184
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423200"
---
# <a name="dateadd-function-access-custom-web-app"></a>DateAdd 函数 (Access 自定义 Web 应用) 

返回具有指定数字间隔的指定 (正整数或负整数) 添加到该日期的指定日期部分。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateAdd** (*DatePart*、 *Number*、 *Date*)  
  
**DateAdd** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *DatePart*  <br/> |将整数  *添加到的 Date*  部分。 有关有效设置的列表，请参阅"备注"部分。  <br/> |
| *Number*  <br/> |是可解析为添加到  *DatePart*  of Date 的整数的  *表达式*  。 如果指定一个包含小数部分的值，则分数将被截去。  <br/> |
| *Date*  <br/> |可以解析为"日期/时间"值的表达式。 *Date* 参数表达式、列表达式、用户定义的变量或字符串文本。  <br/> |
   
## <a name="remarks"></a>备注

下表列出了所有有效的  *DatePart*  参数。 
  
|***DatePart***|
|:-----|
|**year** <br/> |
|**quarter** <br/> |
|**month** <br/> |
|**dayofyear** <br/> |
|**day** <br/> |
|**week** <br/> |
|**hour** <br/> |
|**minute** <br/> |
|**second** <br/> |
|**毫秒** <br/> |
   
## <a name="example"></a>示例

下面的表达式计算当月的最后一天。
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today())+1,0))`

下面的表达式计算上个月的最后一天。
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today()),0))`


