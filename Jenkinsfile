config {
	daysToKeep = 21
	cronTrigger = '@weekend'
}

node() {
	git.checkout { }

	dockerfile.validate { }

	def img = dockerfile.build {
		registry = 'docker.topicusonderwijs.nl'
		name = 'applicationscaler'
		tag = '1.0.0'
	}
	
	dockerfile.publish {
		image = img
		baseTag = false
	}
}

