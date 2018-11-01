---
title: 步骤 1：设置 Visual Basic 项目
TOCTitle: 'Step 1: Set Up the Visual Basic Project'
ms:assetid: 1b8195c9-60c8-18a2-3fa2-ffdeed370748
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248954(v=office.15)
ms:contentKeyID: 48543544
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 31b81c762f192f8a56e56baf0c5e0ae5b6b6fadf
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868649"
---
# <a name="step-1-set-up-the-visual-basic-project"></a><span data-ttu-id="89029-102">步骤 1：设置 Visual Basic 项目</span><span class="sxs-lookup"><span data-stu-id="89029-102">Step 1: Set Up the Visual Basic Project</span></span>


<span data-ttu-id="89029-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="89029-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="step-1-set-up-the-visual-basic-project"></a><span data-ttu-id="89029-104">步骤 1：设置 Visual Basic 项目</span><span class="sxs-lookup"><span data-stu-id="89029-104">Step 1: Set Up the Visual Basic Project</span></span>

<span data-ttu-id="89029-105">在该方案中，假设系统上装有 Microsoft Visual Basic 6.0 或更高版本、ADO 2.5 或更高版本以及 Microsoft OLE DB Provider for Internet Publishing。</span><span class="sxs-lookup"><span data-stu-id="89029-105">In this scenario, it is assumed that you have Microsoft Visual Basic 6.0 or later, ADO 2.5 or later, and the Microsoft OLE DB Provider for Internet Publishing installed on your system.</span></span>

<span data-ttu-id="89029-106">**创建 ADO 项目**</span><span class="sxs-lookup"><span data-stu-id="89029-106">**To create an ADO project**</span></span>

1.  <span data-ttu-id="89029-107">在 Microsoft Visual Basic 中，新建一个标准 EXE 项目。</span><span class="sxs-lookup"><span data-stu-id="89029-107">In Microsoft Visual Basic, create a new Standard EXE project.</span></span>

2.  <span data-ttu-id="89029-108">从**项目**菜单中，选择**引用**。</span><span class="sxs-lookup"><span data-stu-id="89029-108">From the **Project** menu, choose **References**.</span></span>

3.  <span data-ttu-id="89029-109">选择 **"Microsoft ActiveX Data Objects 2.5 Library**"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="89029-109">Select **"Microsoft ActiveX Data Objects 2.5 Library**" and click **OK**.</span></span>

<span data-ttu-id="89029-110">**在主窗体上插入控件**</span><span class="sxs-lookup"><span data-stu-id="89029-110">**To insert controls on the main form**</span></span>

1.  <span data-ttu-id="89029-p101">向 Form1 中添加一个 ListBox 控件。将它的 **Name** 属性设置为 lstMain。</span><span class="sxs-lookup"><span data-stu-id="89029-p101">Add a ListBox control to Form1. Set its **Name** property to lstMain.</span></span>

2.  <span data-ttu-id="89029-p102">向 Form1 中添加另一个 ListBox 控件。将它的 **Name** 属性设置为 lstDetails。</span><span class="sxs-lookup"><span data-stu-id="89029-p102">Add another ListBox control to Form1. Set its **Name** property to lstDetails.</span></span>

3.  <span data-ttu-id="89029-p103">向 Form1 中添加一个 TextBox 控件。将它的 **Name** 属性设置为 txtDetails。</span><span class="sxs-lookup"><span data-stu-id="89029-p103">Add a TextBox control to Form1. Set its **Name** property to txtDetails.</span></span>

