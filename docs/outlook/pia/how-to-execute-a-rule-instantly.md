---
title: 立即执行规则
TOCTitle: Execute a rule instantly
ms:assetid: b41031d5-aa81-40e2-ae78-b45a2f79eb5d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424476(v=office.15)
ms:contentKeyID: 55119919
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a6bb6ac5422b9785660cb3ec0020c01244002c6b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320368"
---
# <a name="execute-a-rule-instantly"></a><span data-ttu-id="4c9b5-102">立即执行规则</span><span class="sxs-lookup"><span data-stu-id="4c9b5-102">Execute a rule instantly</span></span>

<span data-ttu-id="4c9b5-103">此代码示例展示了如何使用 [Rule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) 对象的 [Execute(Object, Object, Object, Object)](https://msdn.microsoft.com/library/bb645769\(v=office.15\)) 方法立即执行规则。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-103">This example shows how to execute a rule instantly by using the [Execute(Object, Object, Object, Object)](https://msdn.microsoft.com/library/bb645769\(v=office.15\)) method of the [Rule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) object.</span></span>

## <a name="example"></a><span data-ttu-id="4c9b5-104">示例</span><span class="sxs-lookup"><span data-stu-id="4c9b5-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="4c9b5-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="4c9b5-p101">通过对 **Rule** 对象调用 **Execute** 方法可使规则得到立即执行。 **Execute** 方法的参数是可选的；如果没有指定参数，则规则将应用于收件箱中的所有邮件，但不包括收件箱的子文件夹，并且将使用参数的默认值。下表列出了 **Execute** 方法的可选参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-p101">You can cause a rule to execute immediately by calling the **Execute** method on the **Rule** object. The parameters to the **Execute** method are optional; if they are not specified, the rule will be applied to all messages in the Inbox but not to the subfolders of the Inbox, and default values for the parameters will be used. The following table lists the default values for the optional parameters of the **Execute** method.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4c9b5-109">参数</span><span class="sxs-lookup"><span data-stu-id="4c9b5-109">Parameter</span></span></p></th>
<th><p><span data-ttu-id="4c9b5-110">默认值</span><span class="sxs-lookup"><span data-stu-id="4c9b5-110">Default value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c9b5-111">ShowProgress</span><span class="sxs-lookup"><span data-stu-id="4c9b5-111">ShowProgress</span></span></p></td>
<td><p><span data-ttu-id="4c9b5-112">False</span><span class="sxs-lookup"><span data-stu-id="4c9b5-112">False</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c9b5-113">文件夹</span><span class="sxs-lookup"><span data-stu-id="4c9b5-113">Folder</span></span></p></td>
<td><p><span data-ttu-id="4c9b5-114">收件箱</span><span class="sxs-lookup"><span data-stu-id="4c9b5-114">Inbox</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c9b5-115">IncludeSubfolders</span><span class="sxs-lookup"><span data-stu-id="4c9b5-115">IncludeSubfolders</span></span></p></td>
<td><p><span data-ttu-id="4c9b5-116">False</span><span class="sxs-lookup"><span data-stu-id="4c9b5-116">False</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c9b5-117">RuleExecuteOption</span><span class="sxs-lookup"><span data-stu-id="4c9b5-117">RuleExecuteOption</span></span></p></td>
<td><p><span data-ttu-id="4c9b5-118">OlRuleExecuteOption.olRuleExecuteAllMessages</span><span class="sxs-lookup"><span data-stu-id="4c9b5-118">OlRuleExecuteOption.olRuleExecuteAllMessages</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4c9b5-119">可使用“规则和警报向导”来取消执行规则。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-119">You can cancel a rule execution by using the Rules and Alerts Wizard.</span></span> <span data-ttu-id="4c9b5-120">也可以通过下面的方法来取消执行规则：先将 *ShowProgress* 参数设置为 **true**，再取消进度对话框。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-120">You can also cancel a rule execution by setting the *ShowProgress* parameter to **true** and then canceling the progress dialog box.</span></span> <span data-ttu-id="4c9b5-121">取消进度对话框后，**Execute** 便会返回错误。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-121">Once you cancel the progress dialog box, **Execute** will return an error.</span></span>

<span data-ttu-id="4c9b5-122">在下面的代码示例中，ExecuteManagerRule 获取通过主题[创建规则：存档来自经理的邮件项，并标记这些项以供跟进](how-to-create-a-rule-to-file-mail-items-from-a-manager-and-flag-them-for-follow-up.md)中的 CreateManagerRule 过程创建的规则。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-122">In the following code example, ExecuteManagerRule gets the rule that was created in the procedure CreateManagerRule from the topic [Create a Rule to File Mail Items from a Manager and Flag Them for Follow-Up](how-to-create-a-rule-to-file-mail-items-from-a-manager-and-flag-them-for-follow-up.md).</span></span> <span data-ttu-id="4c9b5-123">然后，ExecuteManagerRule 检查规则是否不是空引用。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-123">ExecuteManagerRule then checks whether the rule is not a null reference.</span></span> <span data-ttu-id="4c9b5-124">如果规则不是空引用，ExecuteManagerRule 便会对规则调用采用默认参数（即立即执行规则）的 **Execute** 方法。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-124">If the rule is not a null reference, ExecuteManagerRule calls the **Execute** method on the rule with default parameters, instantly executing the rule.</span></span>

> [!NOTE]
> <span data-ttu-id="4c9b5-p104">[!注释] 不管 [Enabled](https://msdn.microsoft.com/library/bb609147(v=office.15)) 属性是否返回 **true**，若要立即应用规则，请使用 **Rule.Execute** 方法。若要为当前会话和其他会话应用规则，请同时使用 **Rule.Enabled** 属性和 [Save(Object)](https://msdn.microsoft.com/library/bb610738(v=office.15)) 方法。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-p104">To apply a rule once, regardless of whether the [Enabled](https://msdn.microsoft.com/library/bb609147(v=office.15)) property returns **true**, use the **Rule.Execute** method. To apply the rule for the current session and beyond the current session, use both the **Rule.Enabled** property and the [Save(Object)](https://msdn.microsoft.com/library/bb610738(v=office.15)) method.</span></span>

<span data-ttu-id="4c9b5-127">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-127">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="4c9b5-128">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-128">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="4c9b5-129">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="4c9b5-129">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void ExecuteManagerRule()
{
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;
    if (currentUser.Type == "EX")
    {
        try
        {
            string managerName = currentUser.
                GetExchangeUser().GetExchangeUserManager().Name;
            Outlook.Rule managerRule =
                Application.Session.DefaultStore.GetRules()[managerName];
            if (managerRule != null)
            {
                managerRule.Execute(false, Type.Missing,
                    Type.Missing, Type.Missing);
            }
        }
        catch (Exception ex)
        {
            Debug.WriteLine(ex.Message);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="4c9b5-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c9b5-130">See also</span></span>

- [<span data-ttu-id="4c9b5-131">规则</span><span class="sxs-lookup"><span data-stu-id="4c9b5-131">Rules</span></span>](rules.md)

