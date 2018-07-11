---
title: 更新函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8a8c52c9-81b9-4d10-b42b-e360c67bcf4e
description: 返回在指定的字段中是否尝试了插入或更新操作。
ms.openlocfilehash: 1685d9f44bd167571b949a34d6c7b6993e63fbc0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773636"
---
# <a name="update-function-access-custom-web-app"></a>更新函数 （访问自定义 web 应用程序）

返回在指定的字段中是否尝试了插入或更新操作。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **更新**（*列*） 
  
**更新**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Column*  <br/> |要检查插入或更新操作的域的名称。  <br/> |
   
## <a name="remarks"></a>说明

**更新**函数无论插入或更新尝试是否成功，则返回 TRUE。 
  

