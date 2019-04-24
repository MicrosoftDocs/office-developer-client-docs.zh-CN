---
title: TimeFromParts 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7f631b7e-6e3c-46dc-a05f-6a07f9a91268
description: 根据指定的部分返回时间值。
ms.openlocfilehash: 8e2105140056bc65e9af0a6eda6e40fc44caed1a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304247"
---
# <a name="timefromparts-function-access-custom-web-app"></a>TimeFromParts 函数 (Access 自定义 web 应用程序)

根据指定的部分返回时间值。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **TimeFromParts**(*小时*、*分钟*、*秒*) 
  
**TimeFromParts**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Hour*  <br/> |指定小时的整数表达式。  <br/> |
| *Minute*  <br/> |指定分钟的整数表达式。  <br/> |
| *Second*  <br/> |指定秒的整数表达式。  <br/> |
   
## <a name="see-also"></a>另请参阅

 **TimeFromParts**返回完全初始化的时间值。 如果参数无效, 则会引发错误。 如果有任何参数为 null, 则返回 null。 
  

