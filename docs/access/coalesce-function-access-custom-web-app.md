---
title: '将 Access 自定义 (应用程序功能与) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 92a7cc0a-1f9f-4969-8439-56a8d18e1347
description: 从参数列表中返回非 NULL 的第一个表达式。
ms.openlocfilehash: af309d2330f5c3b3999a4d99d8f2ab2d6d7d61db
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411391"
---
# <a name="coalesce-function-access-custom-web-app"></a>将 Access 自定义 (应用程序功能与) 

从参数列表中返回非 NULL 的第一个表达式。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**Coalesce** (*Value*， [*Value*]， ...，[*Value*])  
  
**Coalesce** 函数包含下列参数 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *值*  <br/> |表达式。  <br/> |
   
## <a name="remarks"></a>备注

如果所有参数都为 NULL， **则 Coalesce** 返回 NULL。 
  
## <a name="example"></a>示例

下面的表达式用作表的验证规则。 该表达式确保在提交记录之前，在"名字、姓氏、电子邮件、移动电话、工作单位电话、住宅电话和公司"字段中输入条目。 如果列出的任何字段留空， **则 Coalesce** 函数将返回 Null，这将违反验证规则。 
  
```vb
Coalesce([First Name],[Last Name],[Email],[Mobile Phone],[Work Phone],[Home Phone],[Company]) Is Not Null
```


