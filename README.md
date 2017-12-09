# CEPSharePoint
SharePoint site for client

This feature is to change the "link url" for search web part results displayed in the "content web part > Item matching a tag". The link should point to allitems.aspx.

//Custom View

(function () {

    var requestCtx = {};
    requestCtx.Templates = {};

    requestCtx.Templates.Fields = {
        'LinkTitle': {'View': titleFieldTemplate}   
    };

    SPClientTemplates.TemplateManager.RegisterTemplateOverrides(requestCtx);

})();

function titleFieldTemplate(ctx) {
    var id = ctx.CurrentItem.ID;
    var title = ctx.CurrentItem.Title;
    var url = "https://creativeedgeparties.sharepoint.com/sites/phototest1a/Photos/Forms/AllItems.aspx?itemId=" + id;
    return '<a href="' + url + '">' + title + '</a>';
}
