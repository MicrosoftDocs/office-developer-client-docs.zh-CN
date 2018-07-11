---
title: 合并函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 92a7cc0a-1f9f-4969-8439-56a8d18e1347
description: 返回不为 NULL 从参数列表的第一个表达式。
ms.openlocfilehash: cfe6f59c22a89b2a6d211e5f05c2dbf275d8da11
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773447"
---
# <a name="coalesce-function-access-custom-web-app"></a>合并函数 （访问自定义 web 应用程序）

返回不为 NULL 从参数列表的第一个表达式。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**合并**（*值*，[*值*]，...，[*值*]） 
  
**联合**函数包含以下参数 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Value*  <br/> |一个表达式。  <br/> |
   
## <a name="remarks"></a>说明

如果所有参数都均为空，**联合**将返回 NULL。 
  
## <a name="example"></a>示例

以下表达式用作表格的有效性规则。 表达式可确保提交记录之前的项所做的名字，最后一个名称，电子邮件，移动电话，工作电话，家庭电话、 和公司字段中。 如果任一列出的字段为空，则**联合**函数将返回 Null，违反有效性规则。 
  
```vb
Coalesce([First Name],[Last Name],[Email],[Mobile Phone],[Work Phone],[Home Phone],[Company]) Is Not Null
```


