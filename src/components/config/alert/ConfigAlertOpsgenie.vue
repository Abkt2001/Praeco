<template>
  <div>
    <el-form-item label="opsgenie_key" prop="opsgenieKey" required>
      <el-input v-model="opsgenieKey" :disabled="viewOnly" />
      <label>
        The randomly generated API Integration key created by OpsGenie.
      </label>
    </el-form-item>

    <el-form-item label="opsgenie_account" prop="opsgenieAccount">
      <el-input v-model="opsgenieAccount" :disabled="viewOnly" />
      <label>
        The randomly generated API Integration key created by OpsGenie.
      </label>
    </el-form-item>

    <el-form-item label="opsgenie_message" prop="opsgenieMessage">
      <el-input v-model="opsgenieMessage" :disabled="viewOnly" />
      <label>
        Set the OpsGenie message to something other than the rule name. The message can be formatted with fields from the first match e.g. “Error occurred for {app_name} at {timestamp}.”.
      </label>
    </el-form-item>

    <el-form-item label="opsgenie_subject" prop="opsgenieSubject">
      <el-input v-model="opsgenieSubject" :disabled="viewOnly" />
      <label>
        A string used to create the title of the OpsGenie alert. Can use Python string formatting.
      </label>
    </el-form-item>

    <el-form-item label="opsgenie_alias" prop="opsgenieAlias">
      <el-input v-model="opsgenieAlias" :disabled="viewOnly" />
      <label>
        Set the OpsGenie alias. The alias can be formatted with fields from the first match e.g “{app_name} error”.
      </label>
    </el-form-item>

    <el-form-item label="opsgenie_proxy" prop="opsgenieProxy">
      <el-input v-model="opsgenieProxy" :disabled="viewOnly" />
      <label>
        By default ElastAlert 2 will not use a network proxy to send notifications to OpsGenie. Set this option using hostname:port if you need to use a proxy. only supports https.
      </label>
    </el-form-item>

    <el-form-item label="opsgenie_description" prop="opsgenieDescription">
      <el-input v-model="opsgenieDescription" :disabled="viewOnly" />
      <label>
        Set the OpsGenie description to something other than the rule body. The message can be formatted with fields from the first match e.g. “Error occurred for {app_name} at {timestamp}.”.
      </label>
    </el-form-item>
  </div>
</template>

<script>
export default {
  props: ['viewOnly'],

  computed: {
    opsgenieKey: {
      get() {
        return this.$store.state.config.alert.opsgenieKey;
      },
      set(value) {
        this.$store.commit(
          'config/alert/OPSGENIE_KEY',
          value
        );
      }
    },

    opsgenieAccount: {
      get() {
        return this.$store.state.config.alert.opsgenieAccount;
      },
      set(value) {
        this.$store.commit(
          'config/alert/OPSGENIE_ACCOUNT',
          value
        );
      }
    },

    opsgenieMessage: {
      get() {
        return this.$store.state.config.alert.opsgenieMessage;
      },
      set(value) {
        this.$store.commit(
          'config/alert/OPSGENIE_MESSAGE',
          value
        );
      }
    },

    opsgenieSubject: {
      get() {
        return this.$store.state.config.alert.opsgenieSubject;
      },
      set(value) {
        this.$store.commit(
          'config/alert/OPSGENIE_SUBJECT',
          value
        );
      }
    },

    opsgenieAlias: {
      get() {
        return this.$store.state.config.alert.opsgenieAlias;
      },
      set(value) {
        this.$store.commit(
          'config/alert/OPSGENIE_ALIAS',
          value
        );
      }
    },

    opsgenieProxy: {
      get() {
        return this.$store.state.config.alert.opsgenieProxy;
      },
      set(value) {
        this.$store.commit(
          'config/alert/OPSGENIE_PROXY',
          value
        );
      }
    },

    opsgenieDescription: {
      get() {
        return this.$store.state.config.alert.opsgenieDescription;
      },
      set(value) {
        this.$store.commit(
          'config/alert/OPSGENIE_DESCRIPTION',
          value
        );
      }
    },
  },

  methods: {
  }
};
</script>

<style lang="scss">
</style>
