---
title: 如果...然后...其他宏程序块 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 18d28dc1-c41f-47c6-b5c7-258d5f877d01
description: 可以使用 If 宏程序块，根据表达式的值有条件地执行一组操作。
ms.openlocfilehash: 8ac78ff0eaf22c1d821e306654ebfa8fac4ed34a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773457"
---
# <a name="ifthenelse-macro-block-access-custom-web-app"></a>如果...然后...其他宏程序块 （访问自定义 web 应用程序）

可以使用 **If** 宏程序块，根据表达式的值有条件地执行一组操作。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
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

## <a name="setting"></a>设置

对于 **If** 和 ** Else If ** ，以下参数是必需的。 
  
|**操作参数**|**说明**|
|:-----|:-----|
|**Expression** <br/> |您要测试的条件。 它必须是表达式的计算结果为 True 或 False。  <br/> |
   
## <a name="remarks"></a>注释

当您选择 **If** 宏程序块时，会出现一个文本框，可在其中输入代表要测试的条件的表达式。此外，还会出现一个可插入宏操作的组合框，它下面会自动显示文本"End If"。If 和 End If 括起一个区域，可在其中输入操作组或块。仅当您输入的表达式为 True 时，该块才会执行。 
  
表达式进行求值不同的第一个表达式为 false 时，您可以单击**添加 Else If**插入一个可选的**Else If**块。 您必须输入表达式，其计算结果 True 或 False。 在这种情况下，阻止执行仅当表达式为 True 且的第一个表达式为 False。 
  
您可以根据需要向 If 块中添加任意多个 **Else If** 块。 
  
您可以单击**添加其他人**要插入可选的**Else**块。 在这种情况下， **Else**下方插入操作窗体的**Else**块中，仅当上述操作不会执行。 您可以向**If**块添加单个**Else**块。 
  
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
  

