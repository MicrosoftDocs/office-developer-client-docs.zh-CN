---
title: 则 eomonth 将函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: df98bcca-152b-49f2-b4e1-35d68008fb8f
description: 返回的最后一天前的月份或指定的月数。
ms.openlocfilehash: cee42c4e5cb3a24b2e702673238ac9ee09bc7372
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773428"
---
# <a name="eomonth-function-access-custom-web-app"></a>则 eomonth 将函数 （访问自定义 web 应用程序）

返回的最后一天前的月份或指定的月数。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **则 eomonth 将**(*日期*， *NumberOfMonth*) 
  
**则 eomonth 将**包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Date*  <br/> |在日期/时间格式，或接受的文本表示形式日期开始的日期。  <br/> |
| *NumberOfMonth*  <br/> |一个数字，表示的*日期*之前或之后的月数。  <br/> |
   
## <a name="remarks"></a>备注

如果*日期*不是有效日期，**则 eomonth 将**返回错误。 
  
如果*日期*加上*NumberOfMonth*产生无效日期，**则 eomonth 将**返回错误。 
  

