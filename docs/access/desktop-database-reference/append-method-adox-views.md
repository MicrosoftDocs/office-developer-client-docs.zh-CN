---
title: Append 方法（ADOX 视图）
TOCTitle: Append method (ADOX Views)
ms:assetid: 202f1d0a-dc5d-84e5-daf3-3212e5bc6088
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248985(v=office.15)
ms:contentKeyID: 48543655
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9e1a6e14542f267af6a9f5bc58bb2d75a11aac77
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297044"
---
# <a name="append-method-adox-views"></a><span data-ttu-id="04732-102">Append 方法（ADOX 视图）</span><span class="sxs-lookup"><span data-stu-id="04732-102">Append method (ADOX Views)</span></span>

<span data-ttu-id="04732-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="04732-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="04732-104">创建一个新的 [View](view-object-adox.md) 对象，并将其追加到 [Views](views-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="04732-104">Creates a new [View](view-object-adox.md) object and appends it to the [Views](views-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="04732-105">语法</span><span class="sxs-lookup"><span data-stu-id="04732-105">Syntax</span></span>

<span data-ttu-id="04732-106">*视图*。追加*名称*、*命令*</span><span class="sxs-lookup"><span data-stu-id="04732-106">*Views*.Append*Name*, *Command*</span></span>

## <a name="parameters"></a><span data-ttu-id="04732-107">参数</span><span class="sxs-lookup"><span data-stu-id="04732-107">Parameters</span></span>

|<span data-ttu-id="04732-108">参数</span><span class="sxs-lookup"><span data-stu-id="04732-108">Parameter</span></span>|<span data-ttu-id="04732-109">描述</span><span class="sxs-lookup"><span data-stu-id="04732-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="04732-110">*Name*</span><span class="sxs-lookup"><span data-stu-id="04732-110">*Name*</span></span> |<span data-ttu-id="04732-111">**String** 值，指定要创建的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="04732-111">A **String** value that specifies the name of the view to create.</span></span>|
|<span data-ttu-id="04732-112">*Command*</span><span class="sxs-lookup"><span data-stu-id="04732-112">*Command*</span></span> |<span data-ttu-id="04732-113">一个表示要创建的视图的 ADO [Command](command-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="04732-113">An ADO [Command](command-object-ado.md) object that represents the view to create.</span></span>|

## <a name="remarks"></a><span data-ttu-id="04732-114">注解</span><span class="sxs-lookup"><span data-stu-id="04732-114">Remarks</span></span>

<span data-ttu-id="04732-115">使用在 **Command** 对象中指定的名称和属性在数据源中创建一个新视图。</span><span class="sxs-lookup"><span data-stu-id="04732-115">Creates a new view in the data source with the name and attributes specified in the **Command** object.</span></span>

<span data-ttu-id="04732-p101">如果用户指定的命令文本表示过程而非视图，则其行为取决于提供程序。如果该提供程序不支持保留命令，则 **Append** 将失败。</span><span class="sxs-lookup"><span data-stu-id="04732-p101">If the command text that the user specifies represents a procedure rather than a view, the behavior is dependent upon the provider. **Append** will fail if the provider does not support persisting commands.</span></span>

> [!NOTE]
> <span data-ttu-id="04732-p102">使用 OLE DB Provider for Microsoft Jet 时，**Views** 集合的 **Append** 方法将使您可以在 **Command** 参数中指定 **Procedure** 而非 *View*。该 **Procedure** 将添加到数据源，并将添加到 **Views** 集合。执行 **Append** 之后，如果刷新 **Procedures** 和 **Views** 集合，可以看到该 **Procedure** 不再位于 **Views** 集合中，而是出现在 **Procedures** 集合中。</span><span class="sxs-lookup"><span data-stu-id="04732-p102">When using the OLE DB Provider for Microsoft Jet, the **Views** collection **Append** method will allow you to specify a **Procedure** rather than a **View** in the *Command* parameter. The **Procedure** will be added to the data source and will be added to the **Views** collection. After the **Append**, if the **Procedures** and **Views** collections are refreshed, the **Procedure** will no longer be in the **Views** collection and will appear in the **Procedures** collection.</span></span>


