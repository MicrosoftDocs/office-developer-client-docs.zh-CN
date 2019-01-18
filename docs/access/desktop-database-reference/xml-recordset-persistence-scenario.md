---
title: XML 记录集暂留方案
TOCTitle: XML Recordset persistence scenario
ms:assetid: 08f464da-10ba-b649-7571-766a40da2e04
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248825(v=office.15)
ms:contentKeyID: 48543107
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5bae48f3e9b2b5c3967b955c41ba01c634546164
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711530"
---
# <a name="xml-recordset-persistence-scenario"></a><span data-ttu-id="71e2e-102">XML 记录集暂留方案</span><span class="sxs-lookup"><span data-stu-id="71e2e-102">XML Recordset persistence scenario</span></span>

<span data-ttu-id="71e2e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="71e2e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="71e2e-104">在该方案中，您将创建一个 Active Server Pages (ASP) 应用程序，该应用程序将 **Recordset** 对象的内容直接保存到 ASP **Response** 对象中。</span><span class="sxs-lookup"><span data-stu-id="71e2e-104">In this scenario, you will create an Active Server Pages (ASP) application that saves the contents of a **Recordset** object directly to the ASP **Response** object.</span></span>

> [!NOTE]
> <span data-ttu-id="71e2e-105">[!注释] 该方案要求您的服务器上装有 Internet Information Server 5.0 (IIS) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="71e2e-105">This scenario requires that your server have Internet Information Server 5.0 (IIS) or later installed.</span></span>

<span data-ttu-id="71e2e-106">返回的 **Recordset** 使用 [RDS.DataControl](datacontrol-object-rds.md) 显示在 Internet Explorer 中。</span><span class="sxs-lookup"><span data-stu-id="71e2e-106">The returned **Recordset** is displayed in Internet Explorer using an [RDS.DataControl](datacontrol-object-rds.md).</span></span>

<span data-ttu-id="71e2e-107">下列步骤是创建该方案所必需的步骤：</span><span class="sxs-lookup"><span data-stu-id="71e2e-107">The following steps are necessary to create this scenario:</span></span>

1.  <span data-ttu-id="71e2e-108">设置应用程序。</span><span class="sxs-lookup"><span data-stu-id="71e2e-108">Set up the application.</span></span>
2.  <span data-ttu-id="71e2e-109">获取数据。</span><span class="sxs-lookup"><span data-stu-id="71e2e-109">Get the data.</span></span>
3.  <span data-ttu-id="71e2e-110">发送数据。</span><span class="sxs-lookup"><span data-stu-id="71e2e-110">Send the data.</span></span>
4.  <span data-ttu-id="71e2e-111">接收和显示数据。</span><span class="sxs-lookup"><span data-stu-id="71e2e-111">Receive and display the data.</span></span>

## <a name="step-1-set-up-the-application"></a><span data-ttu-id="71e2e-112">步骤 1： 设置应用程序</span><span class="sxs-lookup"><span data-stu-id="71e2e-112">Step 1: Set up the application</span></span>

1. <span data-ttu-id="71e2e-113">创建名为脚本权限**XMLPersist**的 IIS 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="71e2e-113">Create an IIS virtual directory named **XMLPersist** with script permissions.</span></span> 

2. <span data-ttu-id="71e2e-114">在向其虚拟目录点，一个命名的**XMLResponse.asp**，另一个名为**Default.htm**的文件夹中创建两个新的文本文件。</span><span class="sxs-lookup"><span data-stu-id="71e2e-114">Create two new text files in the folder to which the virtual directory points, one named **XMLResponse.asp**, and the other named **Default.htm**.</span></span>


## <a name="step-2-get-the-data"></a><span data-ttu-id="71e2e-115">步骤 2： 获取数据</span><span class="sxs-lookup"><span data-stu-id="71e2e-115">Step 2: Get the data</span></span>

<span data-ttu-id="71e2e-116">在该步骤中，您将编写用来打开 ADO **Recordset** 的代码，并准备将其发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="71e2e-116">In this step, you will write the code to open an ADO **Recordset** and prepare to send it to the client.</span></span> 

1. <span data-ttu-id="71e2e-117">用文本编辑器（如 Windows 记事本）打开 XMLResponse.asp 文件，并插入以下代码：</span><span class="sxs-lookup"><span data-stu-id="71e2e-117">Open the file XMLResponse.asp with a text editor, such as Windows Notepad, and insert the following code:</span></span>

   ```vb 
        
        <%@ language="VBScript" %> 
        
        <!-- #include file='adovbs.inc' --> 
        
        <% 
        Dim strSQL, strCon 
        Dim adoRec  
        Dim adoCon  
        Dim xmlDoc  
        
        ' You will need to change "slqServer" below to the name of the SQL  
        ' server machine to which you want to connect. 
        strCon = "Provider=sqloledb;Data Source=sqlServer;Initial Catalog=Pubs;Integrated Security=SSPI;" 
        Set adoCon = server.createObject("ADODB.Connection") 
        adoCon.Open strCon 
        
        strSQL = "SELECT Title, Price FROM Titles ORDER BY Price" 
        Set adoRec = Server.CreateObject("ADODB.Recordset") 
        adoRec.Open strSQL, adoCon, adOpenStatic, adLockOptimistic, adCmdText 
   ```

2. <span data-ttu-id="71e2e-118">请务必 strCon 中的数据源参数值更改为 Microsoft SQL Server 计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="71e2e-118">Be sure to change the value of the Data Source parameter in strCon to the name of your Microsoft SQL Server computer.</span></span>

3. <span data-ttu-id="71e2e-119">使该文件保持打开状态并转至下一步。</span><span class="sxs-lookup"><span data-stu-id="71e2e-119">Keep the file open and go on to the next step.</span></span>

## <a name="step-3-send-the-data"></a><span data-ttu-id="71e2e-120">步骤 3： 发送数据</span><span class="sxs-lookup"><span data-stu-id="71e2e-120">Step 3: Send the data</span></span>

<span data-ttu-id="71e2e-121">现在您已经拥有一个 **Recordset** ，您将需要通过将它作为 XML 保存到 ASP **Response** 对象中来将其发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="71e2e-121">Now that you have a **Recordset**, you need to send it to the client by saving it as XML to the ASP **Response** object.</span></span> 

1. <span data-ttu-id="71e2e-122">请将以下代码添加到 XMLResponse.asp 的底部：</span><span class="sxs-lookup"><span data-stu-id="71e2e-122">Add the following code to the bottom of XMLResponse.asp:</span></span>

   ```vb 
    
    Response.ContentType = "text/xml" 
    Response.Expires = 0 
    Response.Buffer = False 
    
    
    Response.Write "<?xml version='1.0'?>" & vbNewLine 
    adoRec.save Response, adPersistXML 
    adoRec.Close 
    Set adoRec=Nothing 
    %> 
   ```

   <span data-ttu-id="71e2e-123">请注意，ASP**响应**对象的指定为**Recordset** [保存](save-method-ado.md)方法的目标。</span><span class="sxs-lookup"><span data-stu-id="71e2e-123">Notice that the ASP **Response** object is specified as the destination for the **Recordset** [Save](save-method-ado.md) method.</span></span> <span data-ttu-id="71e2e-124">**Save** 方法的目标可以是支持 **IStream** 接口的任何对象（如 ADO [Stream](stream-object-ado.md) 对象），也可以是包括要将 **Recordset** 保存到的完整路径的文件名。</span><span class="sxs-lookup"><span data-stu-id="71e2e-124">The destination of the **Save** method can be any object that supports the **IStream** interface, such as an ADO [Stream](stream-object-ado.md) object, or a file name that includes the complete path to which the **Recordset** is to be saved.</span></span>

2. <span data-ttu-id="71e2e-125">在转至下一步之前请保存并关闭 XMLResponse.asp。</span><span class="sxs-lookup"><span data-stu-id="71e2e-125">Save and close XMLResponse.asp before going to the next step.</span></span> <span data-ttu-id="71e2e-126">此外将 adovbs.inc 文件复制从 c:\\Program Files\\Common Files\\系统\\Ado 文件夹到了 XMLResponse.asp 文件的同一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="71e2e-126">Also copy the adovbs.inc file from C:\\Program Files\\Common Files\\System\\Ado folder to the same folder where you have the XMLResponse.asp file.</span></span>

## <a name="step-4-receive-and-display-the-data"></a><span data-ttu-id="71e2e-127">步骤 4： 接收和显示数据</span><span class="sxs-lookup"><span data-stu-id="71e2e-127">Step 4: Receive and display the data</span></span>

<span data-ttu-id="71e2e-128">在此步骤中，将 HTML 文件创建与嵌入[rds.DataControl](datacontrol-object-rds.md)对象的 points XMLResponse.asp 文件以获取**记录集**。</span><span class="sxs-lookup"><span data-stu-id="71e2e-128">In this step, you will create an HTML file with an embedded [RDS.DataControl](datacontrol-object-rds.md) object that points at the XMLResponse.asp file to get the **Recordset**.</span></span> 

1. <span data-ttu-id="71e2e-129">使用 Windows 记事本等文本编辑器，打开 default.htm 并添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="71e2e-129">Open default.htm with a text editor, such as Windows Notepad, and add the following code.</span></span> <span data-ttu-id="71e2e-130">将该 URL 中的"sqlserver"替换为您的服务器计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="71e2e-130">Replace "sqlserver" in the URL with the name of your server computer.</span></span>

   ```html 
    
    <HTML> 
    <HEAD><TITLE>ADO Recordset Persistence Sample</TITLE></HEAD> 
    <BODY> 
    
    <TABLE DATASRC="#RDC1" border="1"> 
    <TR> 
    <TD><SPAN DATAFLD="title"></SPAN></TD> 
    <TD><SPAN DATAFLD="price"></SPAN></TD> 
    </TR> 
    </TABLE> 

    <OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID="RDC1"> 
    <PARAM NAME="URL" VALUE="XMLResponse.asp"> 
    </OBJECT> 
    
    </BODY> 
    </HTML> 
   ```

2. <span data-ttu-id="71e2e-131">关闭 default.htm 文件并将其保存到 XMLResponse.asp 所在的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="71e2e-131">Close the default.htm file and save it to the same folder where you saved XMLResponse.asp.</span></span> 

3. <span data-ttu-id="71e2e-132">使用 Internet Explorer 4.0 或更高版本，打开 URL`https://<sqlserver>/XMLPersist/default.htm`并观察结果。</span><span class="sxs-lookup"><span data-stu-id="71e2e-132">Using Internet Explorer 4.0 or later, open the URL `https://<sqlserver>/XMLPersist/default.htm` and observe the results.</span></span> <span data-ttu-id="71e2e-133">数据将显示在绑定的 DHTML 表中。</span><span class="sxs-lookup"><span data-stu-id="71e2e-133">The data is displayed in a bound DHTML table.</span></span> 

4. <span data-ttu-id="71e2e-134">现在打开 URL`https://<sqlserver>/XMLPersist/XMLResponse.asp`并观察结果。</span><span class="sxs-lookup"><span data-stu-id="71e2e-134">Now open the URL `https://<sqlserver>/XMLPersist/XMLResponse.asp` and observe the results.</span></span> <span data-ttu-id="71e2e-135">此时将显示 XML。</span><span class="sxs-lookup"><span data-stu-id="71e2e-135">The XML is displayed.</span></span>




