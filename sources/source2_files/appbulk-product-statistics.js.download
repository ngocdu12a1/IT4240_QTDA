// Có thể sửa function abChangeVariantStats() để thay đổi statistics khi chọn variant
function abChangeVariantStats() {
    $('.single-option-selector').change(function () {
        if (typeof ABProdStats != 'undefined' && typeof ABProdStats.abChangeProductStats != 'undefined') {
            ABProdStats.abChangeProductStats();
        }
    });
}
//

$(document).ready(function () {
    abChangeVariantStats();
});
