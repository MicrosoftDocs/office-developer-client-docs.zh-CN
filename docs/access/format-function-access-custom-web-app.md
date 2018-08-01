---
title: Format 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 550fc235-f0b9-4d8e-805b-ce467821a8c9
description: 返回一个值，根据指定的模式设置格式。
ms.openlocfilehash: 974b56ab8e6bc3f97c1931ba67ca9cd08c3511c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773468"
---
# <a name="format-function-access-custom-web-app"></a>Format 函数 （访问自定义 web 应用程序）

返回一个值，根据指定的模式设置格式。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **格式**（*表达式*，*格式*） 
  
**Format**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Expression*  <br/> |要设置格式的支持的数据类型的表达式。  <br/> |
| *Format*  <br/> | 格式图案。 Format 参数必须包含有效格式字符串，作为标准格式字符串 （例如，"C"或"D"） 或自定义字符的模式的日期和数字值 (例如，"MMMM dd，yyyy (dddd)")。 有关详细信息，请参阅备注。  <br/> |
   
## <a name="remarks"></a>说明

对于*格式*参数，则可以传递与任何以下模式匹配的字符串： 
  
- [标准数字格式字符串](http://msdn.microsoft.com/en-us/library/dwhawy9k%28v=vs.110%29.aspx)
    
- [自定义数字格式字符串](http://msdn.microsoft.com/en-us/library/0c899ak8%28v=vs.110%29.aspx)
    
- [标准的日期和时间格式字符串](http://msdn.microsoft.com/en-us/library/az4se3k1%28v=vs.110%29.aspx)
    
- [自定义日期和时间格式字符串](http://msdn.microsoft.com/en-us/library/8kb3ddd4%28v=vs.110%29.aspx)
    
不能使用**Format**函数在 Access 2013 web 应用程序的以下方面： 
  
- 表级计算的列
    
- UI 宏
    
- 视图 （例如，在窗体） 中的表达式
    

