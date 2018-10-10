---
title: 步骤 2：初始化主列表框
TOCTitle: 'Step 2: Initialize the Main List Box'
ms:assetid: 81e4dcfd-6ee0-b5f9-9ea3-026c38c26bf0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249562(v=office.15)
ms:contentKeyID: 48545967
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f2b6b4d79262796aa8e9090d673a439a550f042c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467949"
---
# <a name="step-2-initialize-the-main-list-box"></a><span data-ttu-id="9392d-102">步骤 2：初始化主列表框</span><span class="sxs-lookup"><span data-stu-id="9392d-102">Step 2: Initialize the Main List Box</span></span>


<span data-ttu-id="9392d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9392d-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="step-2-initialize-the-main-list-box"></a><span data-ttu-id="9392d-104">步骤 2：初始化主列表框</span><span class="sxs-lookup"><span data-stu-id="9392d-104">Step 2: Initialize the Main List Box</span></span>

<span data-ttu-id="9392d-105">**声明全局 Record 和 Recordset 对象**</span><span class="sxs-lookup"><span data-stu-id="9392d-105">**To declare global Record and Recordset objects**</span></span>

  - <span data-ttu-id="9392d-106">将以下代码插入 Form1 的 (General) (Declarations) 中：</span><span class="sxs-lookup"><span data-stu-id="9392d-106">Insert the following code into the (General) (Declarations) for Form1:</span></span>
    
    ```vb 
     
    Option Explicit 
    Dim grec As Record 
    Dim grs As Recordset 
    ```
    
    <span data-ttu-id="9392d-107">上面的代码声明 **Record** 和 **Recordset** 对象的全局对象引用，在该方案的稍后部分将使用这些对象。</span><span class="sxs-lookup"><span data-stu-id="9392d-107">This code declares global object references for **Record** and **Recordset** objects that will be used later in this scenario.</span></span>

<span data-ttu-id="9392d-108">**连接到 URL 并填充 lstMain**</span><span class="sxs-lookup"><span data-stu-id="9392d-108">**To connect to a URL and populate lstMain**</span></span>

  - <span data-ttu-id="9392d-109">将以下代码插入 Form1 的 Form Load 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="9392d-109">Insert the following code into the Form Load event handler for Form1:</span></span>
    
    ```vb 
     
    Private Sub Form_Load() 
        Set grec = New Record 
        Set grs = New Recordset 
        grec.Open "", "URL=https://servername/foldername/", , _ 
            adOpenIfExists Or adCreateCollection 
        Set grs = grec.GetChildren 
        While Not grs.EOF 
            lstMain.AddItem grs(0) 
            grs.MoveNext 
        Wend 
    End Sub 
    ```
    
    <span data-ttu-id="9392d-110">上面的代码实例化全局 **Record** 和 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="9392d-110">This code instantiates the global **Record** and **Recordset** objects.</span></span> <span data-ttu-id="9392d-111">**记录**，grec，打开与指定为**ActiveConnection**的 URL。</span><span class="sxs-lookup"><span data-stu-id="9392d-111">The **Record**, grec, is opened with a URL specified as the **ActiveConnection**.</span></span> <span data-ttu-id="9392d-112">如果该 URL 存在，则将打开 grec；如果该 URL 尚不存在，则将创建 grec。</span><span class="sxs-lookup"><span data-stu-id="9392d-112">If the URL exists, it is opened; if it does not already exist, it is created.</span></span> <span data-ttu-id="9392d-113">请注意，您应当将"https://servername/foldername/"替换为您的环境中的有效 URL。</span><span class="sxs-lookup"><span data-stu-id="9392d-113">Note that you should replace "https://servername/foldername/" with a valid URL from your environment.</span></span> <span data-ttu-id="9392d-114">**记录**的 grec 子级上打开**Recordset**，grs。</span><span class="sxs-lookup"><span data-stu-id="9392d-114">The **Recordset**, grs, is opened on the children of the **Record**, grec.</span></span> <span data-ttu-id="9392d-115">随后，lstMain 将用发布到该 URL 的资源的文件名填充。</span><span class="sxs-lookup"><span data-stu-id="9392d-115">Then lstMain is populated with the file names of the resources published to the URL.</span></span>

