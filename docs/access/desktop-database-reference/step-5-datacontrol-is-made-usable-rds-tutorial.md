---
title: 步骤 5：使用 DataControl（RDS 教程）
TOCTitle: 'Step 5: DataControl is Made Usable (RDS Tutorial)'
ms:assetid: 9eff5732-2743-6891-dfa6-0991645e17ad
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249728(v=office.15)
ms:contentKeyID: 48546672
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1d5b0dfef4d14594c2b2a9b8b57b866e032a07a5
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605651"
---
# <a name="step-5-datacontrol-is-made-usable-rds-tutorial"></a><span data-ttu-id="d3e93-102">步骤 5：使用 DataControl（RDS 教程）</span><span class="sxs-lookup"><span data-stu-id="d3e93-102">Step 5: DataControl is Made Usable (RDS Tutorial)</span></span>


<span data-ttu-id="d3e93-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d3e93-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d3e93-p101">所返回的 **Recordset** 对象已经可以使用。可以像对任何其他 **Recordset** 一样检查、定位或编辑该对象。对 **Recordset** 可以执行的操作取决于相应的环境。Visual Basic 和 Visual C++ 具有一些可视控件，这些控件可以直接或通过启用数据控件间接使用 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="d3e93-p101">The returned **Recordset** object is available for use. You can examine, navigate, or edit it as you would any other **Recordset**. What you can do with the **Recordset** depends on your environment. Visual Basic and Visual C++ have visual controls that can use a **Recordset** directly or indirectly with the aid of an enabling data control.</span></span>

<span data-ttu-id="d3e93-108"><<<<<<< 标头的示例中，如果网页显示在 Microsoft Internet Explorer 中，您可能想要在可视控件中显示的**Recordset**对象的数据。</span><span class="sxs-lookup"><span data-stu-id="d3e93-108"><<<<<<< HEAD For example, if you are displaying a Web page in Microsoft Internet Explorer, you might want to display the **Recordset** object data in a visual control.</span></span> <span data-ttu-id="d3e93-109">网页上的可视控件不能直接访问 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="d3e93-109">Visual controls on a Web page cannot access a **Recordset** object directly.</span></span> <span data-ttu-id="d3e93-110">但是，它们可以通过 **RDS.DataControl** 访问 [Recordset](datacontrol-object-rds.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="d3e93-110">However, they can access the **Recordset** object through the [RDS.DataControl](datacontrol-object-rds.md).</span></span> <span data-ttu-id="d3e93-111">当 **RDS.DataControl** 的 [SourceRecordset](recordset-sourcerecordset-properties-rds.md) 属性设置为 **Recordset** 对象时，RDS.DataControl 便可被可视控件使用。</span><span class="sxs-lookup"><span data-stu-id="d3e93-111">The **RDS.DataControl** becomes usable by a visual control when its [SourceRecordset](recordset-sourcerecordset-properties-rds.md) property is set to the **Recordset** object.</span></span>
<span data-ttu-id="d3e93-112">=== 例如，如果显示网页的 Microsoft Internet Explorer 中，您可能想要在可视控件中显示的**Recordset**对象的数据。</span><span class="sxs-lookup"><span data-stu-id="d3e93-112">======= For example, if you are displaying a webpage in Microsoft Internet Explorer, you might want to display the **Recordset** object data in a visual control.</span></span> <span data-ttu-id="d3e93-113">网页上的可视控件不能直接访问**Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="d3e93-113">Visual controls on a webpage cannot access a **Recordset** object directly.</span></span> <span data-ttu-id="d3e93-114">但是，它们可以通过 **RDS.DataControl** 访问 [Recordset](datacontrol-object-rds.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="d3e93-114">However, they can access the **Recordset** object through the [RDS.DataControl](datacontrol-object-rds.md).</span></span> <span data-ttu-id="d3e93-115">当 **RDS.DataControl** 的 [SourceRecordset](recordset-sourcerecordset-properties-rds.md) 属性设置为 **Recordset** 对象时，RDS.DataControl 便可被可视控件使用。</span><span class="sxs-lookup"><span data-stu-id="d3e93-115">The **RDS.DataControl** becomes usable by a visual control when its [SourceRecordset](recordset-sourcerecordset-properties-rds.md) property is set to the **Recordset** object.</span></span>
>>>>>>> <span data-ttu-id="d3e93-116">master</span><span class="sxs-lookup"><span data-stu-id="d3e93-116">master</span></span>

<span data-ttu-id="d3e93-117">可视控件对象的 **DATASRC** 参数必须设置为 **RDS.DataControl** ，它的 **DATAFLD** 属性必须设置为 **Recordset** 对象字段（列）。</span><span class="sxs-lookup"><span data-stu-id="d3e93-117">The visual control object must have its **DATASRC** parameter set to the **RDS.DataControl**, and its **DATAFLD** property set to a **Recordset** object field (column).</span></span>

<span data-ttu-id="d3e93-118">在本教程中，设置 **SourceRecordset** 属性：</span><span class="sxs-lookup"><span data-stu-id="d3e93-118">In this tutorial, set the **SourceRecordset** property:</span></span>

```vb 
 
Sub RDSTutorial5() 
 Dim DS as New RDS.DataSpace 
 Dim RS as ADODB.Recordset 
 Dim DC as New RDS.DataControl 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors") 
 DC.SourceRecordset = RS ' Visual controls can now bind to DC. 
... 
```

