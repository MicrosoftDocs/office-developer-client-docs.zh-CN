---
title: 步骤 2：初始化主列表框
TOCTitle: 'Step 2: Initialize the Main List Box'
ms:assetid: 81e4dcfd-6ee0-b5f9-9ea3-026c38c26bf0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249562(v=office.15)
ms:contentKeyID: 48545967
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3505c2726da3f2f2f01d179c97cde5a1d7b635ba
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869895"
---
# <a name="step-2-initialize-the-main-list-box"></a><span data-ttu-id="4dc63-102">步骤 2：初始化主列表框</span><span class="sxs-lookup"><span data-stu-id="4dc63-102">Step 2: Initialize the Main List Box</span></span>


<span data-ttu-id="4dc63-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4dc63-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="step-2-initialize-the-main-list-box"></a><span data-ttu-id="4dc63-104">步骤 2：初始化主列表框</span><span class="sxs-lookup"><span data-stu-id="4dc63-104">Step 2: Initialize the Main List Box</span></span>

<span data-ttu-id="4dc63-105">**声明全局 Record 和 Recordset 对象**</span><span class="sxs-lookup"><span data-stu-id="4dc63-105">**To declare global Record and Recordset objects**</span></span>

  - <span data-ttu-id="4dc63-106">将以下代码插入 Form1 的 (General) (Declarations) 中：</span><span class="sxs-lookup"><span data-stu-id="4dc63-106">Insert the following code into the (General) (Declarations) for Form1:</span></span>
    
    ```vb 
     
    Option Explicit 
    Dim grec As Record 
    Dim grs As Recordset 
    ```
    
    <span data-ttu-id="4dc63-107">上面的代码声明 **Record** 和 **Recordset** 对象的全局对象引用，在该方案的稍后部分将使用这些对象。</span><span class="sxs-lookup"><span data-stu-id="4dc63-107">This code declares global object references for **Record** and **Recordset** objects that will be used later in this scenario.</span></span>

<span data-ttu-id="4dc63-108">**连接到 URL 并填充 lstMain**</span><span class="sxs-lookup"><span data-stu-id="4dc63-108">**To connect to a URL and populate lstMain**</span></span>

  - <span data-ttu-id="4dc63-109">将以下代码插入 Form1 的 Form Load 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="4dc63-109">Insert the following code into the Form Load event handler for Form1:</span></span>
    
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
    
    <span data-ttu-id="4dc63-110">上面的代码实例化全局 **Record** 和 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="4dc63-110">This code instantiates the global **Record** and **Recordset** objects.</span></span> <span data-ttu-id="4dc63-111">**记录**，grec，打开与指定为**ActiveConnection**的 URL。</span><span class="sxs-lookup"><span data-stu-id="4dc63-111">The **Record**, grec, is opened with a URL specified as the **ActiveConnection**.</span></span> <span data-ttu-id="4dc63-112">如果该 URL 存在，则将打开 grec；如果该 URL 尚不存在，则将创建 grec。</span><span class="sxs-lookup"><span data-stu-id="4dc63-112">If the URL exists, it is opened; if it does not already exist, it is created.</span></span> <span data-ttu-id="4dc63-113">请注意，您应当将"https://servername/foldername/"替换为您的环境中的有效 URL。</span><span class="sxs-lookup"><span data-stu-id="4dc63-113">Note that you should replace "https://servername/foldername/" with a valid URL from your environment.</span></span> <span data-ttu-id="4dc63-114">**记录**的 grec 子级上打开**Recordset**，grs。</span><span class="sxs-lookup"><span data-stu-id="4dc63-114">The **Recordset**, grs, is opened on the children of the **Record**, grec.</span></span> <span data-ttu-id="4dc63-115">随后，lstMain 将用发布到该 URL 的资源的文件名填充。</span><span class="sxs-lookup"><span data-stu-id="4dc63-115">Then lstMain is populated with the file names of the resources published to the URL.</span></span>

