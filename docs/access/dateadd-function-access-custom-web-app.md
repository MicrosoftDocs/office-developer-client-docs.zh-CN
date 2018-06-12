---
title: DateAdd 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7174c585-86e1-42a3-bb7f-d6641001b0f2
description: 返回指定数字的时间间隔 （正整数或负整数） 与指定的日期添加到该日期的指定的日期部分。
ms.openlocfilehash: a2baa58a2ccab7d030750d03d4fddb84e8eb8ff7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773463"
---
# <a name="dateadd-function-access-custom-web-app"></a>DateAdd 函数 （访问自定义 web 应用程序）

返回指定数字的时间间隔 （正整数或负整数） 与指定的日期添加到该日期的指定的日期部分。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateAdd**(*DatePart*，*号码*，*日期*) 
  
**DateAdd**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *DatePart*  <br/> |*日期*向其中添加的整数部分。 引用有效设置列表的备注部分。  <br/> |
| *编号*  <br/> |是可以解析为添加到*日期* *DatePart*一个整数值的表达式。 如果使用小数部分指定一个值，则将被截断分数。  <br/> |
| *日期*  <br/> |一个可解析为日期/时间值的表达式。 *日期*参数表达式、 列表达式、 用户定义的变量或字面字符串。  <br/> |
   
## <a name="remarks"></a>备注

下表列出了所有有效的*日期部分*参数。 
  
|***DatePart***|
|:-----|
|**year** <br/> |
|**季度** <br/> |
|**month** <br/> |
|**dayofyear** <br/> |
|**一天** <br/> |
|**周** <br/> |
|**小时** <br/> |
|**分钟** <br/> |
|**第二个** <br/> |
|**毫秒** <br/> |
   
## <a name="example"></a>示例

以下表达式计算当前月份的最后一天。
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today())+1,0))`

以下表达式计算上个月的最后一天。
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today()),0))`


