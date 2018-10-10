---
title: 步骤 1：设置 Visual Basic 项目
TOCTitle: 'Step 1: Set Up the Visual Basic Project'
ms:assetid: 1b8195c9-60c8-18a2-3fa2-ffdeed370748
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248954(v=office.15)
ms:contentKeyID: 48543544
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f608d0dadb44a6ddea7a60123d2d6950bc9627cb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466392"
---
# <a name="step-1-set-up-the-visual-basic-project"></a>步骤 1：设置 Visual Basic 项目


**适用于**： Access 2013 |Office 2013

## <a name="step-1-set-up-the-visual-basic-project"></a>步骤 1：设置 Visual Basic 项目

在该方案中，假设系统上装有 Microsoft Visual Basic 6.0 或更高版本、ADO 2.5 或更高版本以及 Microsoft OLE DB Provider for Internet Publishing。

**创建 ADO 项目**

1.  在 Microsoft Visual Basic 中，新建一个标准 EXE 项目。

2.  从**项目**菜单中，选择**引用**。

3.  选择 **"Microsoft ActiveX Data Objects 2.5 Library**"，然后单击**确定**。

**在主窗体上插入控件**

1.  向 Form1 中添加一个 ListBox 控件。将它的 **Name** 属性设置为 lstMain。

2.  向 Form1 中添加另一个 ListBox 控件。将它的 **Name** 属性设置为 lstDetails。

3.  向 Form1 中添加一个 TextBox 控件。将它的 **Name** 属性设置为 txtDetails。

