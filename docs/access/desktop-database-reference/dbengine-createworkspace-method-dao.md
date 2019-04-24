---
title: CreateWorkspace 方法 (DAO) DBEngine
TOCTitle: CreateWorkspace Method
ms:assetid: a7d73771-9420-0448-99e6-d6c4aa78683a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821374(v=office.15)
ms:contentKeyID: 48546888
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052966
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 9cd84b6b5441edda2042ce0a63ae25b2cf399bd2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294345"
---
# <a name="dbenginecreateworkspace-method-dao"></a><span data-ttu-id="7914c-102">CreateWorkspace 方法 (DAO) DBEngine</span><span class="sxs-lookup"><span data-stu-id="7914c-102">DBEngine.CreateWorkspace method (DAO)</span></span>

<span data-ttu-id="7914c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7914c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7914c-104">创建新的 **[Workspace](workspace-object-dao.md)** 对象。</span><span class="sxs-lookup"><span data-stu-id="7914c-104">Creates a new **[Workspace](workspace-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="7914c-105">语法</span><span class="sxs-lookup"><span data-stu-id="7914c-105">Syntax</span></span>

<span data-ttu-id="7914c-106">*表达式*。CreateWorkspace (***Name***、 ***UserName***、 ***Password***、 ***UseType***)</span><span class="sxs-lookup"><span data-stu-id="7914c-106">*expression* .CreateWorkspace(***Name***, ***UserName***, ***Password***, ***UseType***)</span></span>

<span data-ttu-id="7914c-107">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="7914c-107">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="7914c-108">参数</span><span class="sxs-lookup"><span data-stu-id="7914c-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7914c-109">名称</span><span class="sxs-lookup"><span data-stu-id="7914c-109">Name</span></span></p></th>
<th><p><span data-ttu-id="7914c-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="7914c-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="7914c-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="7914c-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="7914c-112">说明</span><span class="sxs-lookup"><span data-stu-id="7914c-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7914c-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="7914c-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="7914c-114">必需</span><span class="sxs-lookup"><span data-stu-id="7914c-114">Required</span></span></p></td>
<td><p><span data-ttu-id="7914c-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="7914c-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="7914c-116">一个 <strong>String</strong>，对新的 <strong>Workspace</strong> 对象进行唯一命名。</span><span class="sxs-lookup"><span data-stu-id="7914c-116">A <strong>String</strong> that uniquely names the new <strong>Workspace</strong> object.</span></span> <span data-ttu-id="7914c-117">有关有效<strong>工作区</strong>名称的详细信息, 请参阅<strong><a href="connection-name-property-dao.md">Name</a></strong>属性。</span><span class="sxs-lookup"><span data-stu-id="7914c-117">See the <strong><a href="connection-name-property-dao.md">Name</a></strong> property for details on valid <strong>Workspace</strong> names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7914c-118"><em>UserName</em></span><span class="sxs-lookup"><span data-stu-id="7914c-118"><em>UserName</em></span></span></p></td>
<td><p><span data-ttu-id="7914c-119">必需</span><span class="sxs-lookup"><span data-stu-id="7914c-119">Required</span></span></p></td>
<td><p><span data-ttu-id="7914c-120"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="7914c-120"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="7914c-121">一个 <strong>String</strong> 类型的值，用于标识新的 <strong>Workspace</strong> 对象的所有者。</span><span class="sxs-lookup"><span data-stu-id="7914c-121">A <strong>String</strong> that identifies the owner of the new <strong>Workspace</strong> object.</span></span> <span data-ttu-id="7914c-122">有关详细信息，请参阅 <strong>UserName</strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="7914c-122">See the <strong>UserName</strong> property for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7914c-123"><em>Password</em></span><span class="sxs-lookup"><span data-stu-id="7914c-123"><em>Password</em></span></span></p></td>
<td><p><span data-ttu-id="7914c-124">必需</span><span class="sxs-lookup"><span data-stu-id="7914c-124">Required</span></span></p></td>
<td><p><span data-ttu-id="7914c-125"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="7914c-125"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="7914c-126">包含新<strong>Workspace</strong>对象的密码的<strong>字符串</strong>。</span><span class="sxs-lookup"><span data-stu-id="7914c-126">A <strong>String</strong> containing the password for the new <strong>Workspace</strong> object.</span></span> <span data-ttu-id="7914c-127">密码最多可包含20个字符, 并且可以包含除 ASCII 字符 0 (null) 以外的任何字符。</span><span class="sxs-lookup"><span data-stu-id="7914c-127">The password can be up to 20 characters long and can include any characters except ASCII character 0 (null).</span></span></p>
<p><span data-ttu-id="7914c-128"><strong>注意</strong>: 请使用组合了大小写字母、数字和符号的强密码。</span><span class="sxs-lookup"><span data-stu-id="7914c-128"><strong>NOTE</strong>: Use strong passwords that combine upper- and lowercase letters, numbers, and symbols.</span></span> <span data-ttu-id="7914c-129">弱密码不会混合这些元素。</span><span class="sxs-lookup"><span data-stu-id="7914c-129">Weak passwords don't mix these elements.</span></span> <span data-ttu-id="7914c-130">强密码：Y6dh!et5。</span><span class="sxs-lookup"><span data-stu-id="7914c-130">Strong password: Y6dh!et5.</span></span> <span data-ttu-id="7914c-131">弱密码：House27。</span><span class="sxs-lookup"><span data-stu-id="7914c-131">Weak password: House27.</span></span> <span data-ttu-id="7914c-132">请使用可以记住的强密码，这样就不必记录密码了。</span><span class="sxs-lookup"><span data-stu-id="7914c-132">Use a strong password that you can remember so that you don't have to write it down.</span></span></p>
</td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7914c-133"><em>UseType</em></span><span class="sxs-lookup"><span data-stu-id="7914c-133"><em>UseType</em></span></span></p></td>
<td><p><span data-ttu-id="7914c-134">可选</span><span class="sxs-lookup"><span data-stu-id="7914c-134">Optional</span></span></p></td>
<td><p><span data-ttu-id="7914c-135"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="7914c-135"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="7914c-136"><strong><a href="workspacetypeenum-enumeration-dao.md">WorkspaceTypeEnum</a></strong>值之一。</span><span class="sxs-lookup"><span data-stu-id="7914c-136">One of the <strong><a href="workspacetypeenum-enumeration-dao.md">WorkspaceTypeEnum</a></strong> values.</span></span></p>
<p><span data-ttu-id="7914c-137"><strong>注意</strong>: Microsoft Access 2013 中不支持 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="7914c-137"><strong>NOTE</strong>: ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="7914c-138">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="7914c-138">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
</td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="7914c-139">返回值</span><span class="sxs-lookup"><span data-stu-id="7914c-139">Return value</span></span>

<span data-ttu-id="7914c-140">Workspace</span><span class="sxs-lookup"><span data-stu-id="7914c-140">Workspace</span></span>

## <a name="remarks"></a><span data-ttu-id="7914c-141">注解</span><span class="sxs-lookup"><span data-stu-id="7914c-141">Remarks</span></span>

<span data-ttu-id="7914c-142">一旦使用 **CreateWorkspace** 方法来创建新的 **Workspace** 对象，将启动一个 **Workspace** 会话，并且您可以在应用程序中引用该 **Workspace** 对象。</span><span class="sxs-lookup"><span data-stu-id="7914c-142">Once you use the **CreateWorkspace** method to create a new **Workspace** object, a **Workspace** session is started, and you can refer to the **Workspace** object in your application.</span></span>

<span data-ttu-id="7914c-p106">**Workspace** 对象不是永久性的，不能保存到磁盘中。一旦创建了 **Workspace** 对象，就不能改动此对象的任何属性设置，但在将 **Workspace** 对象追加到 [**Workspaces**](workspaces-collection-dao.md) 集合之前，可以修改 **Name** 属性。</span><span class="sxs-lookup"><span data-stu-id="7914c-p106">**Workspace** objects aren't permanent, and you can't save them to disk. Once you create a **Workspace** object, you can't alter any of its property settings, except for the **Name** property, which you can modify before appending the **Workspace** object to the **[Workspaces](workspaces-collection-dao.md)** collection.</span></span>

<span data-ttu-id="7914c-p107">您不必将新的 **Workspace** 对象追加到集合就可以使用该对象。仅当需要通过 **Workspaces** 集合引用新创建的 **Workspace** 对象时，才需要追加该对象。</span><span class="sxs-lookup"><span data-stu-id="7914c-p107">You don't have to append the new **Workspace** object to a collection before you can use it. You append a newly created **Workspace** object only if you need to refer to it through the **Workspaces** collection.</span></span>

<span data-ttu-id="7914c-147">要从 **Workspaces** 集合中删除 **Workspace** 对象，请关闭所有打开的数据库和连接，然后对 **Workspace** 对象使用 **[Close](connection-close-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="7914c-147">To remove a **Workspace** object from the **Workspaces** collection, close all open databases and connections and then use the **[Close](connection-close-method-dao.md)** method on the **Workspace** object.</span></span>

## <a name="example"></a><span data-ttu-id="7914c-148">示例</span><span class="sxs-lookup"><span data-stu-id="7914c-148">Example</span></span>

<span data-ttu-id="7914c-p108">以下示例使用 **CreateWorkspace** 方法创建 Microsoft Access 工作区，并随后列出该工作区的属性。</span><span class="sxs-lookup"><span data-stu-id="7914c-p108">This example uses the **CreateWorkspace** method to createMicrosoft Access workspace. It then lists the properties of the workspace.</span></span>

```vb 
Sub CreateWorkspaceX() 
 
   Dim wrkAcc As Workspace 
   Dim wrkLoop As Workspace 
   Dim prpLoop As Property 
 
   DefaultType = dbUseJet 
   ' Create an unnamed Workspace object of the type  
   ' specified by the DefaultType property of DBEngine  
   ' (dbUseJet). 
   Set wrkAcc = CreateWorkspace("", "admin", "") 
 
   ' Enumerate Workspaces collection. 
   Debug.Print "Workspace objects in Workspaces collection:" 
   For Each wrkLoop In Workspaces 
      Debug.Print "  " & wrkLoop.Name 
   Next wrkLoop 
 
   With wrkAcc 
      ' Enumerate Properties collection of Microsoft Access  
      ' workspace. 
      Debug.Print _ 
         "Properties of unnamed Microsoft Access workspace" 
      On Error Resume Next 
      For Each prpLoop In .Properties 
         Debug.Print "  " & prpLoop.Name & " = " & prpLoop 
      Next prpLoop 
      On Error GoTo 0 
   End With 
 
   wrkAcc.Close 
 
End Sub 
 
```

