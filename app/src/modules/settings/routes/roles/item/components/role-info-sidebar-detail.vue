<template>
	<sidebar-detail icon="info_outline" :title="$t('information')" close>
		<dl v-if="!isNew && role">
			<div>
				<dt>{{ $t('primary_key') }}</dt>
				<dd>{{ role.id }}</dd>
			</div>
		</dl>

		<v-divider />

		<div class="page-description" v-html="md($t('page_help_settings_roles_item'))" />
	</sidebar-detail>
</template>

<script lang="ts">
import { defineComponent, PropType } from '@vue/composition-api';
import { md } from '@/utils/md';

export default defineComponent({
	props: {
		isNew: {
			type: Boolean,
			default: false,
		},
		role: {
			type: Object as PropType<any>,
			default: null,
		},
	},
	setup() {
		return { md };
	},
});
</script>

<style lang="scss" scoped>
.v-divider {
	margin: 20px 0;
}
</style>
