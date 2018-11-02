---
title: DBEngine.DefaultType 属性 (DAO)
TOCTitle: DefaultType Property
ms:assetid: b4371f3e-1ce0-1d0f-93a8-0c5329b510ab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822060(v=office.15)
ms:contentKeyID: 48547217
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053580
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ec8dbc1e758b19c15c1a08b9936fa3c00acabde6
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925655"
---
# <a name="dbenginedefaulttype-property-dao"></a><span data-ttu-id="56e6a-102">DBEngine.DefaultType 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="56e6a-102">DBEngine.DefaultType property (DAO)</span></span>


<span data-ttu-id="56e6a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="56e6a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="56e6a-104">设置或返回一个值，该值指示下一个创建的 **[Workspace](workspace-object-dao.md)** 对象将要使用的工作区类型。</span><span class="sxs-lookup"><span data-stu-id="56e6a-104">Sets or returns a value that indicates what type of workspace will be used by the next **[Workspace](workspace-object-dao.md)** object created.</span></span>

## <a name="syntax"></a><span data-ttu-id="56e6a-105">语法</span><span class="sxs-lookup"><span data-stu-id="56e6a-105">Syntax</span></span>

<span data-ttu-id="56e6a-106">*表达式*。DefaultType</span><span class="sxs-lookup"><span data-stu-id="56e6a-106">*expression* .DefaultType</span></span>

<span data-ttu-id="56e6a-107">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="56e6a-107">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="56e6a-108">注解</span><span class="sxs-lookup"><span data-stu-id="56e6a-108">Remarks</span></span>

<span data-ttu-id="56e6a-109">该设置值或返回值可以是 **[WorkspaceTypeEnum](workspacetypeenum-enumeration-dao.md)** 常量之一。</span><span class="sxs-lookup"><span data-stu-id="56e6a-109">The setting or return value can be one of the of the **[WorkspaceTypeEnum](workspacetypeenum-enumeration-dao.md)** constants.</span></span>


> [!NOTE]
> <span data-ttu-id="56e6a-110">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="56e6a-110">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="56e6a-111">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="56e6a-111">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>

<span data-ttu-id="56e6a-112">通过设置**[CreateWorkspace](dbengine-createworkspace-method-dao.md)** 方法的 type 参数可以为单个**工作区**中重写设置。</span><span class="sxs-lookup"><span data-stu-id="56e6a-112">The setting can be overridden for a single **Workspace** by setting the type argument to the **[CreateWorkspace](dbengine-createworkspace-method-dao.md)** method.</span></span>

