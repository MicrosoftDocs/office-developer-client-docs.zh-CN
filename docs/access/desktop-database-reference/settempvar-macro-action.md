---
title: SetTempVar 宏操作
TOCTitle: SetTempVar Macro Action
ms:assetid: 9c3b7bee-02c5-efbf-1276-4c4a1f7802d9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198102(v=office.15)
ms:contentKeyID: 48546593
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm150219
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 32bf1ff8f660bbc9f38c9764f560c0897041ab45
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468054"
---
# <a name="settempvar-macro-action"></a>SetTempVar 宏操作


**适用于**： Access 2013 |Office 2013



可以使用 **SetTempVar** 操作创建一个临时变量并将其设置为一个特定值。然后，该变量可以在后续操作中作为条件或参数使用，也可以在其他宏、事件过程中或者窗体或报表上使用该变量。

## <a name="setting"></a>设置

**SetTempVar** 操作具有下列参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Name</strong></p></td>
<td><p>请输入临时变量的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>Expression</strong></p></td>
<td><p>输入将用于设置为临时变量的值的表达式。 不要在前对表达式与等 (<strong>=</strong>) 登录。 您可以单击<strong>生成</strong>按钮 <img src="media/access-build-button.gif" title="buildbut_ZA06047218" alt="buildbut_ZA06047218" /> ，以便使用表达式生成器设置此参数。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

- 一次最多可以定义 255 个临时变量。如果您不删除临时变量，它将一直保留在内存中，直到您关闭数据库。在使用完临时变量后，最好将它们删除。要删除单个临时变量，请使用 **[RemoveTempVar](removetempvar-macro-action.md)** 操作，并将其参数设置为要删除的临时变量的名称。如果您有多个临时变量，并且想同时将它们全部删除，请使用 **RemoveAllTempVars** 操作。

- 临时变量是全局性的。 在创建了一个临时变量后，可以在事件过程、Visual Basic for Applications (VBA) 模块、查询或表达式中引用它。 例如，如果您创建一个名为*MyVar*的临时变量，您可以使用变量作为控件源对于文本框使用以下语法：
    
  `=[TempVars]![MyVar]`
    
  > [!NOTE]
  > [!注释] 在宏、查询和事件过程中，不需要在表达式前面放等号。
 
  还可以在任何加载项或被引用的数据库中引用临时变量。

- 要在 VBA 模块中运行 **SetTempVar** 操作，请使用 **TempVars** 对象的 **Add** 方法。

## <a name="example"></a>示例

下面的宏演示如何使用 **SetTempVar** 操作创建临时变量，在条件和消息框中使用该临时变量，然后删除该临时变量。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>条件</p></th>
<th><p>操作</p></th>
<th><p>参数</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>SetTempVar</strong></p></td>
<td><p><strong>名称</strong>： MyVar<strong>表达式</strong>： InputBox (&quot;输入非零数。&quot;)</p></td>
</tr>
<tr class="even">
<td><p>[TempVars] ！[MyVar]&lt; &gt;0</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>: =&quot;您输入&quot; &amp; [TempVars] ！[MyVar]&amp; &quot;.&quot;<strong>发嘟嘟声</strong>： <strong>YesType</strong>：<strong>信息</strong></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>RemoveTempVar</strong></p></td>
<td><p><strong>名称</strong>：MyVar</p></td>
</tr>
</tbody>
</table>

