---
title: 'Update Function (Access custom web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8a8c52c9-81b9-4d10-b42b-e360c67bcf4e
description: 返回是否尝试对指定字段执行 INSERT 或 UPDATE 操作。
ms.openlocfilehash: 20e1b87be857f302f36244a6733625dc477da912
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410915"
---
# <a name="update-function-access-custom-web-app"></a>Update Function (Access custom web app) 

返回是否尝试对指定字段执行 INSERT 或 UPDATE 操作。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **更新** (*列*)  
  
**Update** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Column*  <br/> |要检查 INSERT 或 UPDATE 操作字段的名称。  <br/> |
   
## <a name="remarks"></a>备注

无论 **INSERT** 或 UPDATE 尝试是否成功，Update 函数都返回 TRUE。 
  

