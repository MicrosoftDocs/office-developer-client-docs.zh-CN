---
title: GoToControl 宏操作（Access 自定义 Web 应用）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 6c286821-67d6-4d96-973a-bca7934c7672
description: 可以使用 GoToControl 操作将焦点移动到打开视图的当前记录中的指定控件。
ms.openlocfilehash: 2368933a6277615554a565d3bdd973f7d1f366f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302574"
---
# <a name="gotocontrol-macro-action-access-custom-web-app"></a>GoToControl 宏操作（Access 自定义 Web 应用）

可以使用 **GoToControl** 操作将焦点移动到打开视图的当前记录中的指定控件。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**GoToControl** 操作具有以下参数。 
  
|**操作参数**|**说明**|
|:-----|:-----|
|**控件名称** <br/> |希望获得焦点的字段或控件的名称。 这是必需参数。  <br/> |
   
## <a name="remarks"></a>说明

当你希望特定字段或控件获得焦点时，可以使用此操作。 你可以使用此操作以根据特定的条件在表单中导航。 例如，如果用户输入婚姻控件不能在健康保险窗体，焦点可以自动跳过配偶姓名控件并移动到下一个控件。
  

