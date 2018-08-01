---
title: DateWithTimeFromParts 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: aa97cbaa-8b14-42e3-a098-938ebe0769eb
description: 返回日期和时间基于指定的年、 月、 日和时间。
ms.openlocfilehash: 8cc1fbe700d18c04d944793bcea889424b0cff3f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773407"
---
# <a name="datewithtimefromparts-function-access-custom-web-app"></a>DateWithTimeFromParts 函数 （访问自定义 web 应用程序）

返回日期和时间基于指定的年、 月、 日和时间。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateWithTimeFromParts**（*年*、*月*、*日*、*小时*、*分钟*、*第二个*） 
  
**DateWithTimeFromParts**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *year()*  <br/> |指定一年的整数表达式。  <br/> |
| *month*  <br/> |指定某个月份的整数表达式。  <br/> |
| *日。*  <br/> |指定一天的整数表达式。  <br/> |
| *小时*  <br/> |整型表达式，指定小时。  <br/> |
| *分钟*  <br/> |整型表达式，指定分钟。  <br/> |
| *第二节*  <br/> |整型表达式，指定秒。  <br/> |
   
## <a name="remarks"></a>说明

**DateWithTimeFromParts**返回一个完全初始化的日期/时间值。 如果参数不是有效的则会引发错误。 如果需要参数均为空，则返回 Null。 
  

