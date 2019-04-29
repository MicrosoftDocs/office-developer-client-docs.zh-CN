---
title: If .。。然后 .。。Else 宏块 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 18d28dc1-c41f-47c6-b5c7-258d5f877d01
description: 可以使用 If 宏程序块，根据表达式的值有条件地执行一组操作。
ms.openlocfilehash: 6fe82e2c42f8e5d93cdc26798e7572e32d6cdc7e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434492"
---
# <a name="ifthenelse-macro-block-access-custom-web-app"></a>If .。。然后 .。。Else 宏块 (Access 自定义 web 应用程序)

可以使用 **If** 宏程序块，根据表达式的值有条件地执行一组操作。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

```vb
IfexpressionThen 
 Insert macro actions here ... 
Else Ifexpression  
 Insert macro actions here ... 
Else 
 Insert macro actions here ... 
End If
```

## <a name="setting"></a>Setting

对于 **If** 和 ** Else If ** ，以下参数是必需的。 
  
|**操作参数**|**说明**|
|:-----|:-----|
|**Expression** <br/> |要测试的条件。 它必须是一个计算结果为 True 或 False 的表达式。  <br/> |
   
## <a name="remarks"></a>说明

当您选择 **If** 宏程序块时，会出现一个文本框，可在其中输入代表要测试的条件的表达式。此外，还会出现一个可插入宏操作的组合框，它下面会自动显示文本"End If"。If 和 End If 括起一个区域，可在其中输入操作组或块。仅当您输入的表达式为 True 时，该块才会执行。 
  
To evaluate a different expression when the first expression is false, you can click **Add Else If** to insert an optional **Else If** block. You must enter an expression that evaluates to True or False. In this case, the block executes only if the expression is True and the first expression is False. 
  
您可以根据需要向 If 块中添加任意多个 **Else If** 块。 
  
You can click **Add Else** to insert an optional **Else** block. In this case, the actions that you insert below the **Else** form the **Else** block, which executes only when the actions above do not. You can add a single **Else** block to an **If** block. 
  
在下面的代码示例中，如果 [Status] 的值大于 0，将执行第一个块中的宏操作。如果 [Status] 的值不大于 0，则计算 **Else If** 之后的表达式。如果 [Status] 的值等于 0，将执行 **Else If** 块中的宏操作。最后，如果第一个块和第二个块都不执行，则执行 **Else** 块中的操作。 
  
```vb
If[Status] > 0Then 
 Insert macro actions here ... 
Else If[Status] = 0  
 Insert macro actions here ... 
Else 
 Insert macro actions here ... 
End If
```

您可以嵌套 **If** 块。如果要在第一个表达式为 True 时计算另一个表达式，则应考虑在 **If** 块中嵌套一个 **If** 块。在下面的代码示例中，仅当 [Status] 的值既大于 0  **又**  大于 100 时，才会执行内部 *If* 块。 
  

