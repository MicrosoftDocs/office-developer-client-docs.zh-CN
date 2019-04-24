---
title: DateWithTimeFromParts 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: aa97cbaa-8b14-42e3-a098-938ebe0769eb
description: 返回基于指定的年、月、日和时间的日期和时间。
ms.openlocfilehash: ee995d346ca27e683f342cf3f611c1147997d24e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282139"
---
# <a name="datewithtimefromparts-function-access-custom-web-app"></a>DateWithTimeFromParts 函数 (Access 自定义 web 应用程序)

返回基于指定的年、月、日和时间的日期和时间。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateWithTimeFromParts**(*年*、*月*、*日*、*小时*、*分钟*、*秒*) 
  
**DateWithTimeFromParts**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Year*  <br/> |指定一年的整数表达式。  <br/> |
| *Month*  <br/> |指定一个月的整数表达式。  <br/> |
| *Day*  <br/> |指定一天的整数表达式。  <br/> |
| *Hour*  <br/> |指定小时的整数表达式。  <br/> |
| *Minute*  <br/> |指定分钟的整数表达式。  <br/> |
| *Second*  <br/> |指定秒的整数表达式。  <br/> |
   
## <a name="remarks"></a>注解

**DateWithTimeFromParts**返回完全初始化的日期/时间值。 如果参数无效, 则会引发错误。 如果必需的参数为 null, 则返回 null。 
  

