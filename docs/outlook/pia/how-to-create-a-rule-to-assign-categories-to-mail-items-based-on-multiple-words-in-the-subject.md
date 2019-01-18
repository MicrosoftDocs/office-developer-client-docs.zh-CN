---
title: 创建根据主题中的多个字词为邮件项分配类别的规则
TOCTitle: Create a rule to assign categories to mail items based on multiple words in the subject
ms:assetid: 6e1fa40c-edf3-407c-9e90-99f634fa8e24
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424472(v=office.15)
ms:contentKeyID: 55119918
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f0b8b27eb65ef32f95d5529879dde2721e280e26
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706196"
---
# <a name="create-a-rule-to-assign-categories-to-mail-items-based-on-multiple-words-in-the-subject"></a>创建根据主题中的多个字词为邮件项分配类别的规则

此代码示例展示了如何创建根据主题中的多个字词为邮件项分配类别的规则。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

可以对 Outlook 项进行分类，以简化整理和显示过程。 Outlook 对象模型提供 [Category](https://msdn.microsoft.com/library/bb623480\(v=office.15\)) 对象和 [Categories](https://msdn.microsoft.com/library/bb623535\(v=office.15\)) 集合，用于表示类别。 若要详细了解 Outlook 项的 **Category** 对象和 **Categories** 集合，请参阅[枚举和添加类别](how-to-enumerate-and-add-categories.md)。

可分配包含多个条件的规则（由 [Rule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) 对象表示）。 可以获取或设置表示要计算的条件或要完成的操作的数组。 例如， [TextRuleCondition](https://msdn.microsoft.com/library/bb611271\(v=office.15\)) 对象的 [Text](https://msdn.microsoft.com/library/bb644796\(v=office.15\)) 属性返回或设置一个字符串元素组成的数组，该数组表示要按照规则条件计算的文本。 必须为数组分配一个或多个字符串后才能进行计算。 若要计算数组中分配的多个文本字符串，请使用逻辑 OR 运算。 

可用于获取或设置数组的属性如下：[Address](https://msdn.microsoft.com/library/bb647045\(v=office.15\))、[Categories](https://msdn.microsoft.com/library/bb611021\(v=office.15\))、[Categories](https://msdn.microsoft.com/library/bb612345\(v=office.15\))、[FormName](https://msdn.microsoft.com/library/bb647042\(v=office.15\)) 和 **TextRuleCondition.Text**。 若要详细了解规则，请参阅[创建存档来自经理的邮件项并标记这些项以供跟进的规则](how-to-create-a-rule-to-file-mail-items-from-a-manager-and-flag-them-for-follow-up.md)。

在下面的代码示例中，CreateTextAndCategoryRule 使用 CategoryExists 方法，检查用户邮箱项中是否有任何包含 **Categories** 集合中名称“Office”或“Outlook”的类别。 如果找不到任何类别，便会添加这些类别。 然后，此代码示例创建包含“Office”、“Outlook”和“2007”的字符串数组。 此数组表示要计算的条件。 然后，CreateTextAndCategoryRule 创建以下规则：使用 **TextRuleCondition** 对象的 **Text** 属性和 [RuleConditions](https://msdn.microsoft.com/library/bb610965\(v=office.15\)) 集合的 [BodyOrSubject](https://msdn.microsoft.com/library/bb612744\(v=office.15\)) 属性，检查主题中是否包含此数组中的任何条件，以分配类别。 如果满足条件，则会使用 [RuleActions](https://msdn.microsoft.com/library/bb623146\(v=office.15\)) 对象的 [AssignToCategory](https://msdn.microsoft.com/library/bb610113\(v=office.15\)) 方法将类别 Office 和 Outlook 分配给相应项目。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void CreateTextAndCategoryRule()
{
    if (!CategoryExists("Office"))
    {
        Application.Session.Categories.Add(
            "Office", Type.Missing, Type.Missing);
    }
    if (!CategoryExists("Outlook"))
    {
        Application.Session.Categories.Add(
            "Outlook", Type.Missing, Type.Missing);
    }
    Outlook.Rules rules =
        Application.Session.DefaultStore.GetRules();
    Outlook.Rule textRule =
        rules.Create("Demo Text and Category Rule",
        Outlook.OlRuleType.olRuleReceive);
    Object[] textCondition = 
        { "Office", "Outlook", "2007" };
    Object[] categoryAction = 
        { "Office", "Outlook" };
    textRule.Conditions.BodyOrSubject.Text =
        textCondition;
    textRule.Conditions.BodyOrSubject.Enabled = true;
    textRule.Actions.AssignToCategory.Categories =
        categoryAction;
    textRule.Actions.AssignToCategory.Enabled = true;
    rules.Save(true);
}

// Determines if categoryName exists in Categories collection
private bool CategoryExists(string categoryName)
{
    try
    {
        Outlook.Category category =
            Application.Session.Categories[categoryName];
        if (category != null)
        {
            return true;
        }
        else
        {
            return false;
        }
    }
    catch { return false; }
}
```

## <a name="see-also"></a>另请参阅

- [规则](rules.md)

