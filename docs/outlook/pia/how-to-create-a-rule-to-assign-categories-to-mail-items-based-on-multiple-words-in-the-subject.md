---
title: 创建根据主题中的多个字词为邮件项分配类别的规则
TOCTitle: Create a rule to assign categories to mail items based on multiple words in the subject
ms:assetid: 6e1fa40c-edf3-407c-9e90-99f634fa8e24
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424472(v=office.15)
ms:contentKeyID: 55119918
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 1ff096454aa15a0a45c423913140eb50e6de9678
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406321"
---
# <a name="create-a-rule-to-assign-categories-to-mail-items-based-on-multiple-words-in-the-subject"></a><span data-ttu-id="ce66c-102">创建根据主题中的多个字词为邮件项分配类别的规则</span><span class="sxs-lookup"><span data-stu-id="ce66c-102">Create a rule to assign categories to mail items based on multiple words in the subject</span></span>

<span data-ttu-id="ce66c-103">此代码示例展示了如何创建根据主题中的多个字词为邮件项分配类别的规则。</span><span class="sxs-lookup"><span data-stu-id="ce66c-103">This example shows how to set up a rule that assigns categories to mail items based on multiple words in the subject.</span></span>

## <a name="example"></a><span data-ttu-id="ce66c-104">示例</span><span class="sxs-lookup"><span data-stu-id="ce66c-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="ce66c-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="ce66c-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="ce66c-106">可以对 Outlook 项进行分类，以简化整理和显示过程。</span><span class="sxs-lookup"><span data-stu-id="ce66c-106">In Outlook, items can be categorized for easier organization and display.</span></span> <span data-ttu-id="ce66c-107">Outlook 对象模型提供 [Category](https://msdn.microsoft.com/library/bb623480\(v=office.15\)) 对象和 [Categories](https://msdn.microsoft.com/library/bb623535\(v=office.15\)) 集合，用于表示类别。</span><span class="sxs-lookup"><span data-stu-id="ce66c-107">The Outlook object model provides the [Category](https://msdn.microsoft.com/library/bb623480\(v=office.15\)) object and the [Categories](https://msdn.microsoft.com/library/bb623535\(v=office.15\)) collection to represent categories.</span></span> <span data-ttu-id="ce66c-108">若要详细了解 Outlook 项的 **Category** 对象和 **Categories** 集合，请参阅[枚举和添加类别](how-to-enumerate-and-add-categories.md)。</span><span class="sxs-lookup"><span data-stu-id="ce66c-108">For more information about the **Category** object and the **Categories** collection for an Outlook item, see [How to: Enumerate and Add Categories](how-to-enumerate-and-add-categories.md).</span></span>

<span data-ttu-id="ce66c-109">可分配包含多个条件的规则（由 [Rule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) 对象表示）。</span><span class="sxs-lookup"><span data-stu-id="ce66c-109">A rule, represented by a [Rule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) object, can be assigned with multiple conditions.</span></span> <span data-ttu-id="ce66c-110">可以获取或设置表示要计算的条件或要完成的操作的数组。</span><span class="sxs-lookup"><span data-stu-id="ce66c-110">You can get or set an array that represents conditions to be evaluated or actions to be completed.</span></span> <span data-ttu-id="ce66c-111">例如， [TextRuleCondition](https://msdn.microsoft.com/library/bb611271\(v=office.15\)) 对象的 [Text](https://msdn.microsoft.com/library/bb644796\(v=office.15\)) 属性返回或设置一个字符串元素组成的数组，该数组表示要按照规则条件计算的文本。</span><span class="sxs-lookup"><span data-stu-id="ce66c-111">For example, the [Text](https://msdn.microsoft.com/library/bb611271\(v=office.15\)) property of the [TextRuleCondition](https://msdn.microsoft.com/library/bb644796\(v=office.15\)) object returns or sets an array of string elements that represents the text to be evaluated by the rule condition.</span></span> <span data-ttu-id="ce66c-112">必须为数组分配一个或多个字符串后才能进行计算。</span><span class="sxs-lookup"><span data-stu-id="ce66c-112">You must assign an array with one string or multiple strings for evaluation.</span></span> <span data-ttu-id="ce66c-113">若要计算数组中分配的多个文本字符串，请使用逻辑 OR 运算。</span><span class="sxs-lookup"><span data-stu-id="ce66c-113">To evaluate multiple text strings that are assigned in an array, use the logical OR operation.</span></span> 

<span data-ttu-id="ce66c-114">可用于获取或设置数组的属性如下：[Address](https://msdn.microsoft.com/library/bb647045\(v=office.15\))、[Categories](https://msdn.microsoft.com/library/bb611021\(v=office.15\))、[Categories](https://msdn.microsoft.com/library/bb612345\(v=office.15\))、[FormName](https://msdn.microsoft.com/library/bb647042\(v=office.15\)) 和 **TextRuleCondition.Text**。</span><span class="sxs-lookup"><span data-stu-id="ce66c-114">The properties that you can use to get or set an array are as follows: [Address](https://msdn.microsoft.com/library/bb647045\(v=office.15\)) , [Categories](https://msdn.microsoft.com/library/bb611021\(v=office.15\)) , [Categories](https://msdn.microsoft.com/library/bb612345\(v=office.15\)) , [FormName](https://msdn.microsoft.com/library/bb647042\(v=office.15\)) , and **TextRuleCondition.Text**.</span></span> <span data-ttu-id="ce66c-115">若要详细了解规则，请参阅[创建存档来自经理的邮件项并标记这些项以供跟进的规则](how-to-create-a-rule-to-file-mail-items-from-a-manager-and-flag-them-for-follow-up.md)。</span><span class="sxs-lookup"><span data-stu-id="ce66c-115">For more information about rules, see [How to: Create a Rule to File Mail Items from a Manager and Flag Them for Follow-Up](how-to-create-a-rule-to-file-mail-items-from-a-manager-and-flag-them-for-follow-up.md).</span></span>

<span data-ttu-id="ce66c-116">在下面的代码示例中，CreateTextAndCategoryRule 使用 CategoryExists 方法，检查用户邮箱项中是否有任何包含 **Categories** 集合中名称“Office”或“Outlook”的类别。</span><span class="sxs-lookup"><span data-stu-id="ce66c-116">In the following example,   uses the   method to check the user's mail items for any categories by the name "Office" or "Outlook" in the Categories collection.</span></span> <span data-ttu-id="ce66c-117">如果找不到任何类别，便会添加这些类别。</span><span class="sxs-lookup"><span data-stu-id="ce66c-117">If no categories are found, they are added.</span></span> <span data-ttu-id="ce66c-118">然后，此代码示例创建包含“Office”、“Outlook”和“2007”的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="ce66c-118">The example then creates an array of strings that include "Office, "Outlook", and "2007".</span></span> <span data-ttu-id="ce66c-119">此数组表示要计算的条件。</span><span class="sxs-lookup"><span data-stu-id="ce66c-119">This array will represent the conditions to be evaluated.</span></span> <span data-ttu-id="ce66c-120">然后，CreateTextAndCategoryRule 创建以下规则：使用 **TextRuleCondition** 对象的 **Text** 属性和 [RuleConditions](https://msdn.microsoft.com/library/bb610965\(v=office.15\)) 集合的 [BodyOrSubject](https://msdn.microsoft.com/library/bb612744\(v=office.15\)) 属性，检查主题中是否包含此数组中的任何条件，以分配类别。</span><span class="sxs-lookup"><span data-stu-id="ce66c-120"> then creates a rule that assigns categories by examining the subject for any of the conditions in the array by using the Text property of the TextRuleCondition object and the BodyOrSubject property of the RuleConditions collection.</span></span> <span data-ttu-id="ce66c-121">如果满足条件，则会使用 [RuleActions](https://msdn.microsoft.com/library/bb623146\(v=office.15\)) 对象的 [AssignToCategory](https://msdn.microsoft.com/library/bb610113\(v=office.15\)) 方法将类别 Office 和 Outlook 分配给相应项目。</span><span class="sxs-lookup"><span data-stu-id="ce66c-121">If the condition is satisfied, the categories of Office and Outlook are assigned to the item by using the [AssignToCategory](https://msdn.microsoft.com/library/bb623146\(v=office.15\)) method of the [RuleActions](https://msdn.microsoft.com/library/bb610113\(v=office.15\)) object.</span></span>

<span data-ttu-id="ce66c-122">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="ce66c-122">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="ce66c-123">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="ce66c-123">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="ce66c-124">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="ce66c-124">The following line of code shows how to do the import and assignment in C#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ce66c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce66c-125">See also</span></span>

- [<span data-ttu-id="ce66c-126">规则</span><span class="sxs-lookup"><span data-stu-id="ce66c-126">Rules</span></span>](rules.md)

